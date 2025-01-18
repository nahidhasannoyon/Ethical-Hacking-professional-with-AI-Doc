# Hunting Subdomains Part 1

**Understanding Subdomains and Sublist3r**

#### What is a Subdomain?

A subdomain is a subset of a main domain used to organize or separate different sections of a website. For example, in the domain `blog.example.com`, `blog` is the subdomain, and `example.com` is the main domain.

#### Purpose of Subdomains

Subdomains are typically used to:

* Host different sections of a website (e.g., `support.example.com` for support pages).
* Separate environments, such as `dev.example.com` for development.
* Provide specific services, like `mail.example.com` for email.

#### Using Sublist3r to Find Subdomains

`Sublist3r` is a Python-based tool designed to enumerate subdomains of a website. It is commonly used for:

* Security assessments.
* Penetration testing.
* Mapping an organization's web infrastructure.

#### How to Use Sublist3r

1.  Install Sublist3r:

    ```bash
    sudo apt install sublist3r
    ```
2.  Run Sublist3r to enumerate subdomains:

    ```bash
    sublist3r -d domain_url
    ```

    Replace `domain_url` with the target domain, e.g., `example.com`.
3. Sublist3r will generate a list of discovered subdomains, which can be further analyzed.

#### Alternative to Sublist3r: crt.sh

`crt.sh` is a web-based certificate transparency log search tool. It allows you to find subdomains associated with a domain by searching for SSL/TLS certificates.

**How to Use crt.sh**

1. Visit [crt.sh](https://crt.sh/).
2. Enter the target domain in the search bar and submit the query.
3. Review the list of certificates and associated subdomains.

#### Summary

Both Sublist3r and crt.sh are valuable tools for discovering subdomains. Sublist3r provides a command-line option for automated subdomain enumeration, while crt.sh offers a web-based interface for manual searches.
