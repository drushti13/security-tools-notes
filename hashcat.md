# Hashcat

I used Hashcat to crack password hashes using a wordlist. In this room, I learned how Hashcat uses hash modes and attack modes to perform password cracking. I also learned how to identify the correct hash type before starting an attack.

## Commands Used

Basic syntax:

```bash
hashcat -m <hash_type> -a <attack_mode> hashfile wordlist
```

Dictionary attack using rockyou.txt:

```bash
hashcat -m 1000 -a 0 hash.txt /usr/share/wordlists/rockyou.txt
```

View cracked passwords:

```bash
hashcat --show hash.txt
```


* `-m` specifies the hash type.
* `-a` specifies the attack mode.
* Attack mode `0` performs a straight dictionary attack.


## What I Learned

* How to use Hashcat for password cracking.
* How hash modes and attack modes work.
* How to perform dictionary attacks using rockyou.txt.
* Why identifying the correct hash type is important.
* How to view recovered passwords after a successful crack.
