# Umbraco RCE exploit / PoC

> Umbraco CMS 7.12.4 - (Authenticated) Remote Code Execution

## Usage

```
$ python exploit.py -h
usage: exploit.py [-h] --user USER --password PASS --host URL --command CMD

Umbraco authenticated RCE

optional arguments:
  -h, --help                show this help message and exit
  --user USER, -u USER      username / email
  --password PASS, -p PASS  password
  --host URL, -i URL        root URL
  --command CMD, -c CMD     command
```

Example:

```
$ python exploit.py -u admin@example.org -p password123 -i 'http://10.0.0.1' -c ipconfig
```

## Reference

This is a better re-write of [EDB-ID-46153](https://www.exploit-db.com/exploits/46153) and with stdout display.

Tested with python 3.8.
