# John the Ripper 

I used it in TryHackMe John the Ripper Basics room.
This room introduced me to John the Ripper (JtR), a password cracking tool commonly used during penetration testing and CTF challenges. In this room I learned how to identify hashes, crack different hash formats, use custom rules, and extract hashes from protected files such as ZIPs, RARs, and SSH private keys.

## Basic Usage

The general syntax for John is:

```bash
john [options] [hash_file]
```

Most of the time I used:

```bash
john --wordlist=/usr/share/wordlists/rockyou.txt hash.txt
```

To display cracked passwords:

```bash
john --show hash.txt
```

## Identifying Hashes

Before cracking a hash, it's important to identify what format it uses.

I used `hash-id.py` to get possible matches:

```bash
wget https://gitlab.com/kalilinux/packages/hash-identifier/-/raw/kali/master/hash-id.py
python3 hash-id.py
```

One thing I learned is that hash identification tools only provide guesses. Different hash types can have the same length, so context matters when choosing the correct format.

## Cracking Specific Hash Types

When automatic detection didn't work, I specified the format manually:

```bash
john --format=<format> --wordlist=/usr/share/wordlists/rockyou.txt hash.txt
```

Examples:

```bash
john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt hash.txt
john --format=NT --wordlist=/usr/share/wordlists/rockyou.txt ntlm.txt
```

To see all supported formats:

```bash
john --list=formats
```

## NTLM Hashes

NTLM (NTHash) is the hashing format used by Windows systems.

In real-world environments these hashes can be obtained from:

- SAM database
- NTDS.dit
- Mimikatz
- secretsdump.py

To crack an NTLM hash:

```bash
john --format=NT --wordlist=/usr/share/wordlists/rockyou.txt ntlm.txt
```

## Single Crack Mode

Single Crack Mode uses information such as usernames to generate password guesses.

Example:

```bash
john --single --format=raw-sha256 hashes.txt
```

The hash file needs to include the username:

```text
mike:1efee03cdcb96d90ad48ccc7b8666033
```

This allows John to create more targeted password candidates.

## Word Mangling

John can automatically modify words to generate password variations.

For example, if the username is:

```text
Markus
```

John may try:

```text
Markus1
Markus123
MARKUS
Markus!
```

This works because many users create predictable passwords based on their names or usernames.

## Custom Rules

Custom rules allow us to exploit password complexity predictability.

Example rule:

```text
Az"[A-Z]"
```

Using a custom rule called `THMRules`:

```bash
john --rule=THMRules --wordlist=/usr/share/wordlists/rockyou.txt hash.txt
```

## Cracking ZIP Files

First, extract the hash:

```bash
zip2john protected.zip > zip_hash.txt
```

Then crack it:

```bash
john --wordlist=/usr/share/wordlists/rockyou.txt zip_hash.txt
```

## Cracking RAR Files

Extract the hash:

```bash
rar2john protected.rar > rar_hash.txt
```

Crack the password:

```bash
john --wordlist=/usr/share/wordlists/rockyou.txt rar_hash.txt
```

## Cracking SSH Private Keys

Extract the hash from the private key:

```bash
python3 /opt/john/ssh2john.py id_rsa > id_rsa_hash.txt
```

Then crack it:

```bash
john --wordlist=/usr/share/wordlists/rockyou.txt id_rsa_hash.txt
```

## Useful Tools

| Tool | Purpose |
|--------|----------|
| hash-id.py | Identify possible hash types |
| zip2john | Extract hashes from ZIP files |
| rar2john | Extract hashes from RAR files |
| ssh2john | Extract hashes from encrypted SSH keys |
| unshadow | Combine passwd and shadow files |

## What I Learned

- How to identify unknown hashes.
- How to crack hashes using a wordlist.
- How to manually specify hash formats.
- How NTLM hashes are used in Windows environments.
- How Single Crack Mode and word mangling work.
- How to extract hashes from ZIP, RAR, and SSH private key files before cracking them.
- How custom rules can improve password cracking success rates.
