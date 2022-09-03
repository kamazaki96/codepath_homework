# Project 7 - WordPress Pentesting

Time spent: **15** hours spent in total

> Objective: Find, analyze, recreate, and document **three vulnerabilities** affecting an old version of WordPress

## Pentesting Report


### 1. Tile: WordPress 2.5-4.6 - Authenticated Stored Cross-Site Scripting via Image Filename
  - [ ] Summary: A Cross-Site Scripting (XSS) vulnerability has been found in Wordpress upto version 4.2. An Attacker can create a specifically crafted image file name which when, uploaded in the Wordpress. It injects a malicious Javascript code into the application. An Attacker can exploit this vulnerability to perform a wide variery of actions which includes: stealing victims session token, login credentials, cookies, session ID etc. If an attacker gets hold of this sensitive information, they can perform arbitary actions on the victims behalf. 
    
    - Vulnerability types: Cross-Site Scripting (XSS)
    - Tested in version: 4.2
    - Fixed in version: 4.6.1
  - [ ] GIF Walkthrough: 
  <img src = "XSS via ImageFile.gif" alt = "Walkthrough of XSS via ImageFile">
  
  - [ ] Steps to recreate: A WordPress admin needs to upload a malicious file requested by a user the admin trusts. As an attacker you need to do social engineering in order to trick the admin to upload your file. Once the attacker uploaded and views the file, the script is executed. The filename needs to follow the file name: 

```cengizhansahinsumofpwn<img src=a onerror=alert(document.cookie)>.jpg```

  - [ ] Affected source code:
    - [Link 1](https://wpscan.com/vulnerability/e84eaf3f-677a-465a-8f96-ea4cf074c980)
    - [Link 2](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2016-7168)




### 2. Title: WordPress <= 4.2- Unauthenticated Stored Cross-Site Sciripting (XSS)
  - [ ] Summary: The versions of WordPress upto 4.2 are vulnerable to stored Cross-Site Scripting (XSS). An unauthenticated attacker can inject malicious JavaScript in WordPress comments. The script is executed when the comment is viewed by any person. An attacker can do all sort of things, like sending users to another malicious website, steal thier sessions, change thier and admin credentails and many more.

    - Vulnerability types: Cross-Site Scripting (XSS)
    - Tested in version: 4.2
    - Fixed in version: 4.2.1
  - [ ] GIF Walkthrough: 
  <img src = "Unauthenticated XSS (comment).gif" alt = "Walkthrough of Unauthenticated Stored XSS">
  
  - [ ] Steps to recreate: An attacker needs to comment malicious javascript code with html tag in the comment. If the comment text is long enough, it will hbe truncated when inserted into the databse. The truncation results in malformed HTML generated on the page. The following code will help you to recreate: 
 
```<a title='x onmouseover=alert(unescape(/hello%20world/.source)) style=position:absolute;left:0;top:0;width:5000px;height:5000px AAAAAAAAAAAA [64 kb] ...'></a> ```

  - [ ] Affected source code:
    - [Link 1](https://wpscan.com/vulnerability/8051e64b-f73e-45ce-a853-02b8e425155b)
    - [Link 2](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-3440)


### 3. Title: WordPress <= 4.2.2- Authenticated Stored Cross-Site Scirpting (XSS)
  - [ ] Summary: A Stored Cross-Site Scripting in WordPress allows an user with the posting capability to compromise the website. The attacker requires a Contributor or Author level account. The attacker would insert specially formatted HTML containing JavaScript on a WordPress page or a post. The malicious code is executed when an administrator views the page.
    - Vulnerability types: Cross-Site Scripting (XSS)
    - Tested in version: 4.2
    - Fixed in version: 4.2.3
  - [ ] GIF Walkthrough: 
  <img src = "Authenticated XSS (Onloading).gif" alt = "Walkthrough of Authenticated Stored XSS">
  - [ ] Steps to recreate: The attacker needs to gain access to a Contributor or Author level account. They can do so by user enumeration to find username and than do brute force attack in order to find thier password. They can create a WordPress page or post and insert the following code: 

```<body onload=window.location='https://codepath.org/'>```

  - [ ] Affected source code:
  - [Link 1](https://wpscan.com/vulnerability/0f027d7d-674b-4a63-9603-25ea68069c1d)
  - [Link 2](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-5622)
   
## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [2022] [Hanzla Rehmat Younas]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.






