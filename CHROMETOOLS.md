# CHROME TOOLS

Created by Vince Chang </br>

Here is where I post useful information on how to use Google Chrome Developer Tools

#### CHROME DEV TOOLS

- [Mastering Dev Tools](https://masteringdevtools.com/resources)
- [Google Docs](https://developers.google.com/web/tools/chrome-devtools/)
- [Jank Free](http://jankfree.org/)

#### SHORTCUT COMMANDS

`Cmd + o` is shortcut to open file from browser
`Cmd + shift + c / Cmd + shift + i` = open inspect via Chrome
`Cmd + ctrl + space` = emojis

#### NOTES

- Can black box scripts to stop them from running
- Can open your own code in the dev tools and edit it there and it will edit
  your code directly
- Can set breakpoints and step over, step in, functions to see what’s happening
- Testing a website performance:
  - `websitetest.org`
  - Lighthouse built into Chrome Dev Tools
  - [Progressive web app check list](https://developers.google.com/web/progressive-web-apps/checklist)
- **Common Audit Problems**
  - Combine external CSS & JS
  - Enable Gzip Compression (do in node)
  - Compress images
  - Leverage Browser Caching
  - Put CSS in document head
  - Dead code elimination (rule out code we aren’t using if we import ex, all of
    bootstrap but only use part of it)
- **Common Memory Leak Problems**
  - The accidental global
    - Need to set things to var, let or const, if you don’t this now lives on
      the global window
    - The forgotten timer
      - There is a cancel for `settimeout`, `setinterval`, etc
    - Performance tab is best for spotting a memory leak and the Memory tab is
      best for finding the cause
