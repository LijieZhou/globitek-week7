# Project 7 - WordPress Pentesting

Time spent: 10 hours spent in total

> Objective: Find, analyze, recreate, and document three vulnerabilities affecting an old version of WordPress

## Pentesting Report

1. (Required) Authenticated Stored Cross-Site Scripting via Image Filename
  - [x] Summary: Wordpress's media upload function allows multiple media format uploading, such as: audio, video, image, etc. Insufficient validation of the uploaded file name is performed, which leads to potential XSS attack by a crafted file name payload.  
    - Vulnerability types:XSS 
    - Tested in version:WP 4.2.4
    - Fixed in version: 4.6.1
  - [x] GIF Walkthrough: http://i.imgur.com/5i6YT7N.gif
  - [x] Steps to recreate: 
    - Copy and paste this payload and post it in the comment: https://drive.google.com/file/d/0BzsBD-G31f93ZXFWYkUwZTJocjA/view?usp=sharing
  - [ ] Affected source code:
2. (Required) WordPress  Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds
  - [x] Summary: Insufficient satinization in wordpress's embed shortcode function, leading to potential XSS attack.  
    - Vulnerability types: XSS
    - Tested in version: 4.2.4
    - Fixed in version: 4.7.3
  - [x] GIF Walkthrough:http://i.imgur.com/EIPLH79.gif 
  - [x] Steps to recreate: 
    - Copy and paste this payload into a new post: [embed src='https://youtube.com/embed/11111\x3csvg onload=alert(1)\x3e'][/embed]
  - [x] Affected source code:
    - [Link 1](https://developer.wordpress.org/reference/functions/do_shortcode/)
    - [Link 2](https://developer.wordpress.org/reference/functions/wp_embed_register_handler/)
    - [Link 3](https://developer.wordpress.org/reference/classes/wp_embed/autoembed/)
3. (Required) Authenticated Cross-Site Scripting (XSS) via Media File Metadata
  - [x] Summary: The meta information that stored in audio files are not properly sanitized when they are uploaded with editor/administrator. Rendering the wp_playlist_shortcode() function will cause potential XSS attack.  
    - Vulnerability types: XSS 
    - Tested in version: 4.2.4
    - Fixed in version: 4.7.3
  - [x] GIF Walkthrough:http://i.imgur.com/5jDOAHV.gif
  - [x] Steps to recreate: In wordpress's dashboard, choose Media -> Upload New Media. Upload the mp2 file that is in the link attached in the assets. View the newly added meida. 
  - [x] Affected source code:
    - [Link 1](https://developer.wordpress.org/reference/functions/wp_playlist_shortcode/)


## Assets

- Payload of attack 1: https://drive.google.com/file/d/0BzsBD-G31f93ZXFWYkUwZTJocjA/view?usp=sharing

- Payload of attack 2: [embed src='https://youtube.com/embed/11111\x3csvg onload=alert(1)\x3e'][/embed]

- Download link of attack 3: https://drive.google.com/file/d/0BzsBD-G31f93cWhZay11dDREQ0k/view?usp=sharing

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

This assignment really helped me in starting bug hunting in the real world. First, I learnt how to use WPScan. Second, after a few bug reproduction, I realize many vulnerabilities are very similar in style, and you can focus on some "high risk" areas instead of reading the whole codebase. 


    Copyright [2017] Lijie Zhou

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.