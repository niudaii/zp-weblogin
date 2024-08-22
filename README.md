## zp-weblogin
### Overview
`zp-weblogin` is a command-line tool designed for security testing of web login systems. It facilitates automated login attempts while supporting both auto-detection and manual configuration of login selectors.
### Features
- **Auto-Detection & Manual Configuration**: Automatically detect login selectors or manually set them using a configuration file. 
- **Extensive Testing**: Successfully tested on over 50 pages, including ESXI, Jenkins, GitLab, Nacos, and more.
- **Dynamic Password Handling**: Passwords containing `%user%` will be replaced with the corresponding username during the login attempt.
- **Captcha Support**: Supports simple captchas using the [ddddocr](https://gitee.com/fkgeek/ocr_api_server) server. If the target page has a captcha, you must start the OCR server and specify the `--ocr-baseurl`.
### Usage
```
Usage:
  zp-weblogin weblogin [flags]

Examples:
./zp-weblogin weblogin -i http://10.1.1.5:9001
./zp-weblogin weblogin -i http://10.1.1.5:9001 --headless
./zp-weblogin weblogin -i http://10.1.1.5:9001 --selector-file demo.yaml

Flags:
      --crack-all              crack all user and pass
      --delay int              delay time between crack (default 1)
      --headless               headless mode
  -h, --help                   help for weblogin
      --max-attempts int       max attempts (default 3)
      --max-crack-num int      max crack num, 0 is no limit
      --max-crack-time int     max crack time in sec (default 300)
      --ocr-baseurl string     ocr base url (default "http://10.1.2.216:9898")
      --pass strings           pass list, split by comma
      --pass-file string       pass file
      --proxy string           proxy
      --selector-file string   selector file
      --threads int            scan threads (default 3)
      --user strings           user list, split by comma
      --user-file string       user file

Global Flags:
  -i, --inputs strings       inputs split by comma
  -f, --inputs-file string   inputs file split by line(example: -f 'xxx.txt')
      --level string         logger level(debug|info|error) (default "debug")
  -o, --output-file string   output file to write results (default "output.json")

```
### Manual Configuration
demo.yaml
```
userInput: /html/body/div/div/div/div/div[2]/div/input
passwordInput: /html/body/div/div/div/div/div[3]/div/input
loginBtn: /html/body/div/div/div/div/div[4]/button
captchaInput:
captchaImg:
```
### Source Code Status
Due to certain reasons, I am unable to open source the code at this time. However, I warmly welcome everyone to submit issues and suggestions! Your feedback is crucial for me to improve the project.
### Disclaimer
This tool is only intended for security research. Users are responsible for all legal and related liabilities resulting from the use of this tool. The original author does not assume any legal responsibility.
