## Prerequisites

- Bash shell (Linux, macOS, WSL on Windows)
- Basic familiarity with the command line
- No extra dependencies needed — it's a pure Bash script

---

## Usage

1. **Clone the repository** (or download the script):

    ```
    git clone https://github.com/yourusername/Splitter.git
    cd splitter
    ```

2. **Make the script executable:**

    ```
    chmod +x splitter
    ```

3. **Run the tool by piping your HTTPX results file:**

    ```
    cat alive-subdomains.txt | ./splitter
    ```

    Or alternatively, redirect input:

    ```
    ./splitter < alive-subdomains.txt
    ```

4. **Check the created files**, named by HTTP status codes like:

    - `200-subs.txt`
    - `301-subs.txt`
    - `403-subs.txt`
    - `unknown-subs.txt` (for lines without valid codes)

---

## Example Input

https://example.com [200] [93.184.216.34] 
https://test.com [301]  [10.0.0.1] 
https://redirect.com [404] [192.168.1.1]




---

## Example Output Files

- **`200-subs.txt`**

    ```
    https://example.com  [200] [93.184.216.34] 
    https://redirect.com  [200] [192.168.1.1]
    ```

- **`301-subs.txt`**

    ```
    https://redirect.com  [301] [192.168.1.1]
    ```

- **`404-subs.txt`**

    ```
    https://test.com  [404] [10.0.0.1] 
    ```

---

