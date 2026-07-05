# Content Discovery Tools

I used **Gobuster**, **ffuf**, and **dirsearch** during the TryHackMe **Web Application Security Fundamentals** module, mainly in the **Content Discovery** room. These tools helped me discover hidden files, directories, and web pages that were not directly linked on the website. I also used them while solving various TryHackMe and PortSwigger labs whenever content discovery was required.

## Gobuster

Gobuster is a command-line tool used to brute-force directories, files, subdomains, and virtual hosts.

Basic syntax:

```bash
gobuster dir -u http://<target> -w /path/to/wordlist
```

Some useful options:

```bash
gobuster dir -u http://<target> -w /path/to/wordlist -x php,txt,html
```

* `-u` specifies the target URL.
* `-w` specifies the wordlist.
* `-x` searches for specific file extensions.

I mainly used Gobuster to enumerate hidden directories and files on web applications.

## ffuf

ffuf (Fuzz Faster U Fool) is a fast web fuzzer used for content discovery and fuzzing different parts of HTTP requests.

Basic syntax:

```bash
ffuf -u http://<target>/FUZZ -w /path/to/wordlist
```

Find directories:

```bash
ffuf -u http://<target>/FUZZ -w /path/to/wordlist
```

Find virtual hosts:

```bash
ffuf -u http://target -H "Host: FUZZ.target.com" -w /path/to/wordlist
```

Filter responses by status code:

```bash
ffuf -u http://<target>/FUZZ -w /path/to/wordlist -fc 404
```

I found ffuf useful because it is fast, flexible, and allows filtering responses based on status codes, response size, words, and lines.

## dirsearch

dirsearch is another directory and file brute-forcing tool written in Python. It supports recursion, multiple extensions, and many useful options out of the box.

Basic syntax:

```bash
python3 dirsearch.py -u http://<target>
```

Using a custom wordlist:

```bash
python3 dirsearch.py -u http://<target> -w /path/to/wordlist
```

Search with file extensions:

```bash
python3 dirsearch.py -u http://<target> -e php,html,txt
```

I used dirsearch to discover hidden files and directories, especially when I wanted more built-in features like recursive scanning and extension handling.

Although all three tools perform content discovery, each has its own strengths. Gobuster is simple and reliable, ffuf is extremely fast and flexible for fuzzing, and dirsearch provides many useful features for directory enumeration with minimal configuration.
