# Project 7 - WordPress Pentesting

Time spent: **10** hours spent in total

> Objective: Find, analyze, recreate, and document **three vulnerabilities** affecting an old version of WordPress

## Pentesting Report

### 1. Authenticated Stored Cross-Site Scripting (XSS)
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version: 4.1.0
    - Fixed in version: 4.3.0
  - [ ] GIF Walkthrough: ![xss](https://user-images.githubusercontent.com/43329669/98197513-f408c100-1ef4-11eb-8f38-457bada8095d.gif)
  - [ ] Steps to recreate: 
                           1. Login as a user, in this example I am login as an admin 
                           2. Create a new post, or select your existing post if you have, and be able to edit it
                           3. Click on the text component 
                           4. Paste in: <a href="[caption code=" onmouseover=alert('!!!!')  ">Suprise</a>
                           5. Preview the page, and click on the link and the alert box will pop up
  - [ ] Affected source code:
    - [XSS1 Source Code Error](https://core.trac.wordpress.org/changeset/33359)
### 2. Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version: 4.1.0 (4.0.0 - 4.7.2)
    - Fixed in version: 4.7.3
  - [ ] GIF Walkthrough: ![xss3](https://user-images.githubusercontent.com/43329669/98197601-17cc0700-1ef5-11eb-9607-2aae59c08478.gif)
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [XSS2 Source Code Error](https://github.com/WordPress/WordPress/commit/419c8d97ce8df7d5004ee0b566bc5e095f0a6ca8)
### 3. Authenticated Cross-Site Scripting (XSS) via Media File Data
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version: 4.1.0 (3.6.0 - 4.7.2)
    - Fixed in version: 4.73
  - [ ] GIF Walkthrough: ![xss2](https://user-images.githubusercontent.com/43329669/98197553-0420a080-1ef5-11eb-846f-5a1235480e3f.gif)
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [XSS3 Source Code Error](https://core.trac.wordpress.org/browser/branches/4.2/src/wp-admin/media-upload.php)

## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [ScreenToGif](https://www.screentogif.com/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
