# confrontational-spork

### 1. Enumeration
  - [x] Summary: 
    - Vulnerability types: Enumeration
    - Tested in version: Word Press 4.2
    - Fixed in version: 
  - [x] GIF Walkthrough: 
<img src='WordPress Username Enumeration.gif' title='WordPress Username Enumeration' width='' alt='' />
  - [x] Steps to recreate: Start at a WordPress Login page. This vulnerability allows anyone the ability to enumerate a list of valid user names on a WordPress site. Start with typing "admin" and a random password, soon after you are alerted that there is an existing admin account, ultimately making it easier to brute force that admin password. 
  - [ ] Affected source code:
    - [Link 1]
    
    
### 1. Authenticated Stored Cross-Site Scripting (XSS)
  - [X] Summary: inject java script code as a comment 
    - Vulnerability types:XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.1
  - [X] GIF Walkthrough: 
<img src='XSS Exploit.gif' title='XSS Exploit' width='' alt='' />
  - [X] Steps to recreate: <br />
         -Leave a comment with the following content:<br />
         *\<b onmouseover="alert('This is just a vulnerability')">click me!\</b>*
         
  - [X] Affected source code:
    - [Link 1](https://github.com/WordPress/WordPress/blob/4.2-branch/wp-comments-post.php)
    
### 1. (Required) Vulnerability Name
  - [ ] Summary: 
    - Vulnerability types: 
    - Tested in version: 
    - Fixed in version:
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
    
