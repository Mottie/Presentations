<!-- .slide: data-background="#000 url(https://raw.githubusercontent.com/Mottie/Presentations/master/userscripts/images/epic-deadpool-t-shirt-teeturtle-marvel_800x.jpg) no-repeat center 50%" -->

<style>
/* First slide */
#userscripts-bookmarklets { margin-top: 100px; font-size: 1em; }
.reveal section img { border: 0; }
.reveal .image-placeholder { height: 250px; }
.reveal .backgrounds .slide-background[data-background-hash^="url(https"] { background-size: 30% auto !important; }
.reveal h2, .reveal p, .reveal a { text-shadow:1px 1px 2px #000, 0 0 1em #000, 0 0 0.2em #000; }
/* rest of the slides */
.reveal section pre, .reveal section code { white-space: pre-wrap; word-break: break-all; }
.reveal code { color: #FB9632; }
.header-icon { height: 1em; vertical-align: text-bottom; }
.reveal section img { background: transparent; border-color: #333; }
.line-through.visible { text-decoration: line-through; }
.reveal strong { color: #555; font-size: .7em; }
.reveal .small-font, .reveal .bottom-link { font-size: 0.5em; }
.reveal .med-font { font-size: 0.75em; }
.reveal .bottom-link { position:relative; bottom: -100px; }
.reveal .flex-row { display: flex; justify-content: space-evenly; }
.reveal .flex-row img { width: 40%; }
.reveal .flex-row2 { display: flex; }
.reveal .flex-row2 > div { width: 50%; }
.reveal .flex-row2 a { display: block; margin-bottom: 0.5em; }
</style>

## Userscripts &<br>Bookmarklets

<p class="image-placeholder"></p>

Epically customize the web

<a class="bottom-link" href="https://www.teeturtle.com/products/epic-deadpool-shirt">
  https://www.teeturtle.com/products/epic-deadpool-shirt
</a>

---

## Userscripts

- What? Injected JavaScript
- Why? Automatically customize web sites
- How? Userscript manager (built-in?)

<a class="bottom-link" href="https://github.com/OpenUserJs/OpenUserJS.org/wiki/Userscript-Beginners-HOWTO">
  https://github.com/OpenUserJs/OpenUserJS.org/wiki/Userscript-Beginners-HOWTO
</a>

Note: Userscripts used to be built-into browsers, but were removed for security issues. Maybe still available in Chromium (with limitations)?

---

### <img src="https://raw.githubusercontent.com/Mottie/Presentations/master/userscripts/images/warning.png" class="header-icon" /> Warning

- Privacy risks
- Can store & share info (bypass CSP)
- Don't install from untrusted sources
- Examine the code!

---

#### Userscript (JavaScript)

```js
// ==UserScript==
// @name        My Userscript
// @description Try to take over the world!
// @version     0.0.1
// @license     MIT
// @author      Me
// @namespace   my-website.com/me
// @match       https://some-website.com/*
// @grant       none
// ==/UserScript==
(function() {
  'use strict';
  // Your code here...
})();
```

---

### Metadata<sup class="small-font">1</sup>

- `@name` + `@namespace` - unique id
- `@match`, `@include` & `@exclude` - URLs (glob `*`)
- `@grant` - API permissions
- `@require` - JS code libraries to load
- `@resource` - Named resource to load (e.g. CSS)
- `@connect` - whitelist domains for XHR<sup class="small-font">2</sup>

<div class="bottom-link">
  1: <a href="https://wiki.greasespot.net/Metadata_Block">
    https://wiki.greasespot.net/Metadata_Block
  </a>
  <br />
  2: <a href="https://greasyfork.org/en/discussions/development/55737-devs-tampermonkey-s-upcoming-support-of-connect-may-break-scripts-with-gm-xmlhttprequest">
    GM_xmlHttpRequest & @connect 
  </a>
</div>

---

### API <span class="small-font">(common)</span>

- `GM_addStyle` - Inject CSS stylesheet
- `GM_getValue` & `GM_setValue` - Storage
- `GM_xmlhttpRequest` - Cross domain

<a class="bottom-link" href="https://wiki.greasespot.net/Greasemonkey_Manual:API">
  https://wiki.greasespot.net/Greasemonkey_Manual:API
</a>

---

### GitHub Custom Navigation

![](https://raw.githubusercontent.com/Mottie/Presentations/master/userscripts/images/custom-nav-before.png)
![](https://raw.githubusercontent.com/Mottie/Presentations/master/userscripts/images/custom-nav-after.png)
<img src="https://raw.githubusercontent.com/Mottie/Presentations/master/userscripts/images/custom-nav-settings.png" style="height: 250px;" />

<a class="small-font" href="https://greasyfork.org/en/scripts/20830">
  https://greasyfork.org/en/scripts/20830
</a>

---

#### More GitHub Userscripts

<div class="flex-row2">
  <div>
    Before
    <img src="https://raw.githubusercontent.com/Mottie/Presentations/master/userscripts/images/userscript1-before.png">
  </div>

  <div>
    After
    <img src="https://raw.githubusercontent.com/Mottie/Presentations/master/userscripts/images/userscript1-after.png">
    <a href="https://greasyfork.org/en/scripts/20974" style="font-size:14px; color: #91C0F0;">
      https://greasyfork.org/en/scripts/20974
    </a>
    <a href="https://greasyfork.org/en/scripts/18789" style="font-size:14px; color: #FF3230;">
      https://greasyfork.org/en/scripts/18789
    </a>
    <a href="https://greasyfork.org/en/scripts/18141" style="font-size:14px; color: #FB9632;">
      https://greasyfork.org/en/scripts/18141
    </a>
  </div>
</div>

---

### Userscript Managers

![](https://raw.githubusercontent.com/Mottie/Presentations/master/userscripts/images/userscript-support.png)

- [Tampermonkey](https://tampermonkey.net/)
- [Greasemonkey](https://www.greasespot.net/)
  - Firefox only
  - Version 4 not backwards compatible
- [Chromium](https://www.chromium.org/developers/design-documents/user-scripts)
  - No storage
  - Same-origin only

Note: GM4 removes `GM_{api}` and adds `GM.{api}` which uses promises exclusively

---

### Userscript Storehouses/lists

- [GreasyFork.org](https://greasyfork.org)
- [OpenUserJS.org](https://openuserjs.org)
- Hosted anywhere (GitHub, GitLab, Bitbucket, etc)
- [github.com/bvolpato/awesome-userscripts](https://github.com/bvolpato/awesome-userscripts) (curated list)

---

#### Install Userscript

<div class="flex-row">
  <img src="https://raw.githubusercontent.com/Mottie/Presentations/master/userscripts/images/greasyfork.png" />
  <img src="https://raw.githubusercontent.com/Mottie/Presentations/master/userscripts/images/tampermonkey.png" />
</div>

Note: Examine the code at any step

---

### Questions?

---

## Bookmarklets

- What? Run JavaScript (CSP limitations)
- Why? Manually customize stuff
- How? Click a link or browser bookmark

---

### Bookmarklet Creation

```js
var bookmarklet = function(){
  /* code to be executed */
};

var encodedBookmarkletHref = encodeURI(
  'javascript:(' + bookmarklet.toString() + ')();'
);
```

Result


```html
<a href="javascript:(function()%7B/*%20code%20to%20be%20executed%20*/%7D)();">Click me</a>
```

<small class="bottom-link">
  <a href="https://gist.github.com/caseywatts/c0cec1f89ccdb8b469b1">
    https://gist.github.com/caseywatts/c0cec1f89ccdb8b469b1
  </a>
  <br />
  <a href="https://code.tutsplus.com/tutorials/create-bookmarklets-the-right-way--net-18154">
    https://code.tutsplus.com/tutorials/create-bookmarklets-the-right-way--net-18154
  </a>
</small>

---

### Bookmarklet limitations

<ul class="med-font">
  <li>Load external scripts or libraries (CSP limited)</li>
  <li>
    Avoid name collisions
    <ul>
      <li>Wrap code in anonymous function</li>
      <li>Conflicting jQuery versions</li>
    </ul>
  </li>
  <li>Size limit?<sup>1</sup>
    <ul>
      <li>IE11 max 2,047 characters</li>
      <li>> 65,000 in modern browsers</li>
    </ul>
  </li>
</ul>

<div class="bottom-link">
  1:
  <a href="https://stackoverflow.com/a/417184/145346">
    https://stackoverflow.com/a/417184/145346 (size limitation)
  </a>
</div>

---

### Bookmarklet Example

```js
<a href="javascript:(function(){var d=document,j=d.getElementById('__cornify_nodes'),k=null,c='https://cornify.com/js/cornify',l=0;var f=['.js','_run.js'];if(j){cornify_add();}else{k=d.createElement('div');k.id='__cornify_nodes';d.getElementsByTagName('body')[0].appendChild(k);for(;l<f.length;l++){j=d.createElement('script');j.src=c+f[l];k.appendChild(j);}}})();">cornify</a>
```

<img src="https://raw.githubusercontent.com/Mottie/Presentations/master/userscripts/images/cornify.jpg" width="350" />
<br />
<a class="small-font" href="https://www.cornify.com/extras">
  https://www.cornify.com/extras
</a>

---

### Other Bookmarklets

- [Change URL value](https://gist.github.com/Mottie/0e7a119ce0e90d054fef#change-last-value) - go to next/prev GitHub issue
- [The Printliminator](https://css-tricks.github.io/The-Printliminator/) - Cleanup before printing
- [Show anchors](http://www.sensefulsolutions.com/2009/12/show-anchors-bookmarklet.html) - Show all anchors
- [Kick Ass](https://kickassapp.com/) - Asteroids-like in page game
- [Awesome bookmarklets](https://github.com/marcobiedermann/awesome-bookmarklets) - curated list

---

### Questions?

---

### Thanks!

#### Rob Garrison

![](https://raw.githubusercontent.com/Mottie/Presentations/master/userscripts/images/avatar.png)

&#x00ab;w&#x006f;wm&#111;&#x0074;&#116;y&#x40;&#103;m&#x0061;il&#46;c&#111;m&#187;
<br>
[github.com/Mottie](https://github.com/Mottie)
