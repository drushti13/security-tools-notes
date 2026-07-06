# Google Dorking

I used Google Dorking in the TryHackMe **Web Application Security Fundamentals** module, specifically in the **Content Discovery** room and in **Subdomain Enumeration** room. I also used it while solving the **Google Dorking** room, **Searchlight OSINT** CTF, and **Letter** CTF. Along with Google search operators, I learned how tools like **Yandex Search**, **Google Lens**, **Wayback Machine**, **Wappalyzer**, **crt.sh**, **DNSRecon**, and **Sublist3r** can be used during the reconnaissance phase to gather publicly available information about a target.

## Google Dorking

Google Dorking uses search operators to narrow down search results and discover information that may not be easily accessible through normal browsing.

### Common Search Operators

| Operator | Example | Purpose |
|----------|---------|---------|
| `site:` | `site:example.com` | Search only within a specific website |
| `inurl:` | `inurl:admin` | Find pages containing a specific word in the URL |
| `intitle:` | `intitle:login` | Find pages containing a specific word in the page title |
| `filetype:` | `filetype:pdf` | Search for specific file types |

### Combining Search Operators

Find PDF files on a website:

```text
site:example.com filetype:pdf
```

Find admin pages:

```text
site:example.com inurl:admin
```

Find login pages:

```text
site:example.com intitle:login
```

Find indexed subdomains:

```text
site:*.example.com
```

Find documents related to security:

```text
site:example.com filetype:pdf security
```

Search for backup files:

```text
site:example.com filetype:sql
site:example.com filetype:bak
site:example.com filetype:log
```

Search for configuration files:

```text
site:example.com filetype:xml
site:example.com filetype:env
```

I found Google Dorking useful for discovering login portals, public documents, backup files, configuration files, directory listings, and other information that had already been indexed by search engines.

## Certificate Transparency Logs (crt.sh)

I learned that every SSL/TLS certificate issued by a Certificate Authority is recorded in public **Certificate Transparency (CT) logs**. These logs can be searched to discover both current and historical subdomains of a target domain.

I used **crt.sh** to search for certificates associated with a domain and identify subdomains that may not appear through standard search engine results.

Example:

```text
https://crt.sh/?q=example.com
```

Certificate Transparency logs are useful for:

- Discovering subdomains
- Viewing historical certificates
- Finding wildcard certificates
- Expanding the attack surface during reconnaissance

## Sublist3r

I used **Sublist3r** for passive subdomain enumeration. It gathers subdomains from multiple public sources, making it a quick way to build an initial list before performing further enumeration.

Basic usage:

```bash
sublist3r -d example.com
```

Save the results:

```bash
sublist3r -d example.com -o subdomains.txt
```

## DNSRecon

I used **DNSRecon** to enumerate DNS records and discover additional information about a target domain.

Basic usage:

```bash
dnsrecon -d example.com
```

Brute-force subdomains:

```bash
dnsrecon -d example.com -D subdomains.txt -t brt
```

DNSRecon can enumerate:

- DNS records
- Name servers
- Mail servers
- Subdomains
- Zone information

## Yandex Search

I used Yandex Search during the **Searchlight OSINT** CTF for reverse image searches. I found that it often returns better results than Google Lens, especially when identifying locations, landmarks, and visually similar images.

I used it to:

- Find the original source of an image.
- Identify landmarks and locations.
- Discover websites using the same image.
- Gather additional OSINT from publicly available images.

## Google Lens

I used Google Lens alongside Yandex during the **Searchlight OSINT** CTF. It was useful for extracting text from images using OCR and identifying common landmarks, objects, and buildings.

I mainly used it for:

- Reverse image searching.
- Extracting text from images.
- Identifying landmarks and objects.
- Getting additional context about an image.

## Wayback Machine

I used the Wayback Machine during the TryHackMe **Content Discovery** room to view archived versions of websites. It helped me discover pages and content that were no longer available on the live website.

Some useful findings included:

- Old web pages
- Removed directories
- Previous versions of websites
- Information that had been removed from the current site

This showed me how archived content can reveal information that is still useful during reconnaissance.

## Wappalyzer

I used Wappalyzer during the TryHackMe **Content Discovery** room to identify the technologies used by a website before performing further enumeration.

It can detect technologies such as:

- Web servers
- Programming languages
- Content Management Systems (CMS)
- JavaScript frameworks
- Analytics tools
- CDNs
- Hosting providers

Knowing the technology stack helped me understand how the application was built and what areas I should focus on during further testing.
