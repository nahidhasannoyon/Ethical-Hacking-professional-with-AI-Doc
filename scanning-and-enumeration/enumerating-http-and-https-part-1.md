# Enumerating HTTP and HTTPS Part 1

What are HTTP Methods?

HTTP methods are standardized request methods used by clients to communicate with servers over the HTTP/HTTPS protocol. They define the type of operation the client wants to perform. Common HTTP methods include:

* **GET:** Retrieve data from the server (e.g., accessing a webpage).
* **POST:** Submit data to the server (e.g., submitting a form).
* **PUT:** Update or create a resource on the server.
* **DELETE:** Remove a resource from the server.
* **HEAD:** Retrieve the headers of a resource without the body.
* **OPTIONS:** Describe the communication options for a target resource.
* **PATCH:** Apply partial modifications to a resource.

#### Exploring HTTP Scripts with Nmap

**List Available HTTP Scripts**

**Command:**

```bash
ls -al /usr/share/nmap/scripts/ | grep -e "http-"
```

**Purpose:**

* Lists all available Nmap scripts related to HTTP.
* Useful for identifying scripts that can be used for HTTP/HTTPS enumeration and analysis.

**Test HTTP Methods with Nmap**

**Command:**

```bash
nmap -Pn -sV -p 80 -T4 --script http-methods --script-args http-methods.test=all DOMAIN
```

**Purpose:**

* Scans the specified domain or IP to enumerate HTTP methods supported by the server.
* The `--script-args http-methods.test=all` option tests all potential HTTP methods for their availability.
* The `-p 80` specifies port 80 (HTTP) for the scan.

**Explanation of Flags:**

* `-Pn`: Skip host discovery; assume the host is up.
* `-sV`: Perform version detection to identify the software and services running on the target.
* `-T4`: Set a faster timing template for the scan.
* `--script`: Specify the script to use for the scan (in this case, `http-methods`).

#### Summary

Understanding HTTP methods is crucial for identifying misconfigurations and potential vulnerabilities in web applications. Nmap provides robust scripting capabilities, such as the `http-methods` script, to analyze supported methods on a server and detect security risks. Combining these tools with a solid understanding of HTTP methods enhances the effectiveness of HTTP/HTTPS enumeration efforts.
