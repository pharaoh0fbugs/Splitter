## Prerequisites

- Bash shell (Linux, macOS, WSL on Windows)
- Basic familiarity with the command line
- No extra dependencies needed — it's a pure Bash script

---

## Usage

1. **Clone the repository** (or download the script):

    ```
    git clone https://github.com/yourusername/CodeCrack.git
    cd CodeCrack
    ```

2. **Make the script executable:**

    ```
    chmod +x codecrack.sh
    ```

3. **Run the tool by piping your HTTPX results file:**

    ```
    cat alive-subdomains.txt | ./codecrack.sh
    ```

    Or alternatively, redirect input:

    ```
    ./codecrack.sh < alive-subdomains.txt
    ```

4. **Check the created files**, named by HTTP status codes like:

    - `200-subs.txt`
    - `301-subs.txt`
    - `403-subs.txt`
    - `unknown-subs.txt` (for lines without valid codes)

---

## Example Input

https://example.com [1234] [93.184.216.34] [Header1,Header2]
https://test.com [10.0.0.1] [Header3]
https://redirect.com [2345] [192.168.1.1]




---

## Example Output Files

- **`200-subs.txt`**

    ```
    https://example.com  [1234] [93.184.216.34] [Header1,Header2]
    https://redirect.com  [2345] [192.168.1.1]
    ```

- **`301-subs.txt`**

    ```
    https://redirect.com  [2345] [192.168.1.1]
    ```

- **`404-subs.txt`**

    ```
    https://test.com   [10.0.0.1] [Header3]
    ```

---

