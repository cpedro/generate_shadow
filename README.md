# Generate Shadow Password Hash

A simple python script that can be used to generate a password hash that can be
inserted directly into the `/etc/shadow` file on a Linux or Unix system.

Current supported hash methods (from most secure to least):
* SHA512 (Default)
* SHA256
* MD5

## Running:

```
usage: shadow_hash.py [-h] [-m METHOD] [passwords [passwords ...]]

Generate Shadow Hashes.

positional arguments:
  passwords             Password to generate hashes for.

optional arguments:
  -h, --help            show this help message and exit
  -m METHOD, --method METHOD
                        Hashing method to use. (default = SHA512) Available
                        methods are: MD5, BLOWFISH, SHA256, and SHA512
```

* Prompts you for a single password (echo off):
  ```
  $ python3 shadow_hash.py
  ```
* Reads passwords from a file:
  ```
  $ python3 shadow_hash.py < file
  ```
* Reads passwords written to standard output by another command:
  ```
  $ cmd | python3 shadow_hash.py
  ```
* Checks passwords given command line arguments: (**Beware** the password may
  be saved in shell history and that other users on the system may be able to
  observe the command line.)
  ```
  $ python3 shadow_hash.py <password1> [<password2> ...]
  ```
