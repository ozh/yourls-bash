# YOURLS BASH [![Listed in Awesome YOURLS!](https://img.shields.io/badge/Awesome-YOURLS-C5A3BE)](https://github.com/YOURLS/awesome-yourls/)
A simple bash script to shorten URLs with [YOURLS](https://yourls.org) 

![image](https://user-images.githubusercontent.com/223647/120930653-8a50cf80-c6ee-11eb-8972-22197382bfa4.png)

## Installation

```shell
# using wget
$> wget -q https://raw.githubusercontent.com/ozh/yourls-bash/master/yourls
# using curl
$> curl -s -o yourls https://raw.githubusercontent.com/ozh/yourls-bash/master/yourls
```

Then, edit the two parameters at the beginning of the script (`YOURLS_HOST` and `YOURLS_KEY`) to match your setup.

Depending on your setup, you may want to make this file executable (`chmod +x yourls`) and in your $PATH (eg `~/bin` maybe)

## Usage

Shorten a long URL :

```bash
$> yourls https://someverylongdomain.com
https://sho.rt/ef
```

Shorten a long URL and provide a custom keyword and a custom title :

```bash
$> yourls https://someverylongurl.com -k test12 --title "Some title"
https://sho.rt/test12
```

Shorten a URL and receive JSON output, for instance to display with `jq` :
```bash
$> yourls https://example.com -f json | jq
{
  "url": {
    "keyword": "Nzs",
    "url": "https://example.com",
    "title": "Example Domain",
    "date": "2021-06-06 16:03:44",
    "ip": "127.0.0.1"
  },
  "status": "success",
  "message": "http://example.com added to database",
  "title": "Example Domain",
  "shorturl": "http://sho.rt/Nzs",
  "statusCode": 200
}
```

Display help message :
```bash
$> yourls --help
```

## License

Do whatever the hell you want with it



