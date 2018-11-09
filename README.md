# Project 7 - WordPress Pentesting

Time spent: **X** hours spent in total

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

2. (Required) Vulnerability Name or ID

- [ ] Summary:
  - Vulnerability types:
  - Tested in version:
  - Fixed in version:
- [ ] GIF Walkthrough:
- [ ] Steps to recreate:
- [ ] Affected source code:
  - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)

3. (Required) Vulnerability Name or ID

- [ ] Summary:
  - Vulnerability types:
  - Tested in version:
  - Fixed in version:
- [ ] GIF Walkthrough:
- [ ] Steps to recreate:
- [ ] Affected source code:
  - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)

4. (Optional) Vulnerability Name or ID

- [ ] Summary:
  - Vulnerability types:
  - Tested in version:
  - Fixed in version:
- [ ] GIF Walkthrough:
- [ ] Steps to recreate:
- [ ] Affected source code:
  - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)

5. (Optional) Vulnerability Name or ID

- [ ] Summary:
  - Vulnerability types:
  - Tested in version:
  - Fixed in version:
- [ ] GIF Walkthrough:
- [ ] Steps to recreate:
- [ ] Affected source code:
  - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)

## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

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
