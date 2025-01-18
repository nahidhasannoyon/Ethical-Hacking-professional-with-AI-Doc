# Hunting Subdomains Part 2

## Using Subfinder for Subdomain Discovery

`Subfinder` is another tool for subdomain enumeration, known for its speed and efficiency. It gathers subdomains using passive sources and APIs.

**How to Use Subfinder**

1. Install Subfinder following the instructions from its [GitHub repository](https://github.com/projectdiscovery/subfinder).
2.  To enumerate subdomains:

    ```bash
    subfinder -d domain_url
    ```

    Replace `domain_url` with the target domain, e.g., `example.com`.
3.  To increase the number of threads for faster enumeration:

    ```bash
    subfinder -d domain_url -t 20
    ```

    This sets the number of concurrent threads to 20 for faster processing.

#### Alternative to Subfinder: Amass

The OWASP Amass project is another powerful tool for in-depth subdomain enumeration and mapping an organization's attack surface. Find more details on their [GitHub page](https://github.com/owasp-amass/amass).

#### Checking Subdomain Activity with httprobe

`httprobe` is a tool designed to check if subdomains discovered during enumeration are active and accessible.

**How to Use httprobe**

1. Install httprobe following the instructions from its [GitHub repository](https://github.com/tomnomnom/httprobe).
2.  Pipe the list of subdomains into `httprobe` to check for active domains:

    ```bash
    cat subdomains.txt | httprobe
    ```

    Replace `subdomains.txt` with your file containing the list of subdomains.
