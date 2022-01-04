<!-- .slide: data-background="url(https://raw.githubusercontent.com/Mottie/Presentations/master/customizing-the-web/images/unicorn_riding_rainbow_by_k_rui-d3lmuln.gif) no-repeat center 10%" -->

<style>
/* First slide */
#customizing-the-web { margin-top: 150px; }
.reveal section img { border: 0; }
.reveal .backgrounds .slide-background[data-background-hash^="url(https"] { background-size: 30% auto !important; }
.reveal h2, .reveal p, .reveal a { text-shadow:1px 1px 2px #000, 0 0 1em #000, 0 0 0.2em #000; }
.reveal a.smallest { font-size:.5em; bottom: -100px; }
/* rest of the slides */
pre { white-space: pre-wrap; word-break: break-all; }
.reveal section img { background: transparent; border-color: #333; }
.reveal .flex-row { display: flex; }
.reveal .flex-row > div { width: 50%; }
.reveal .flex-row a { display: block; margin-bottom: 0.5em; }
.line-through.visible { text-decoration: line-through; }
.reveal strong { color: #555; font-size: .7em; }
</style>

## Customizing the web

UserStyles & UserScripts

<a href="https://www.deviantart.com/k-rui/art/unicorn-riding-rainbow-217736555" class="smallest">https://www.deviantart.com/k-rui/art/unicorn-riding-rainbow-217736555</a>

---
<!-- .slide: data-background="#222" -->

## UserStyles

- What? Injected CSS
- Why? Change stuff
- How? UserStyle manager

Note: hide ads, change theme or move elements

---

### UserStyle CSS

```css
@-moz-document domain("foo.com"), regexp("^https?://bar\\.com$") {
  body {
    background: #111 !important;
    color: #ddd !important;
  }
  #site-ads {
    display: none !important;
  }
}
```

<small>https://developer.mozilla.org/en-US/docs/Web/CSS/@document</small>

Note: @document has been deprecated

---

### UserCSS (CSS/Stylus)

```css
/* ==UserStyle==
@name        My UserStyle
@version     v0.0.1
@description Make everything rainbows!
@namespace   github.com/me
@author      Me
@license     CC-BY-SA-4.0
@var         color bkgd-color 'Background color' #111
==/UserStyle== */
@-moz-document domain("foo.com"), regexp("^https?://bar\\.com$") {
  body {
    background-color: var(--bkgd-color) !important;
    background-image: url(https://my-site/rainbow.png) !important;
  }
}
```

```css
:root { --bkgd-color: #111 } /* <-- injected & based on user choice */
```

---

<!-- .slide: data-background="#222" -->

### GitHub-Dark UserStyle

<div class="flex-row">
  <div>
    Before
    <img src="https://raw.githubusercontent.com/Mottie/Presentations/master/customizing-the-web/images/userstyle-before.png" />
  </div>

  <div>
    After
    <img src="https://raw.githubusercontent.com/Mottie/Presentations/master/customizing-the-web/images/userstyle-after.png" />
  </div>
</div>

---

#### GitHub-Dark UserCSS Settings

![](https://raw.githubusercontent.com/Mottie/Presentations/master/customizing-the-web/images/github-dark-settings.png)

---

### UserStyles Managers

![](https://raw.githubusercontent.com/Mottie/Presentations/master/customizing-the-web/images/userstyle-support.png)

<ul>
  <li class="fragment" data-fragment-index="1">
    <span class="fragment highlight-red line-through" data-fragment-index="6">
      Stylish (2005)
    </span>
    <span class="fragment" data-fragment-index="6">(SimilarWeb tracking)</span>
  </li>
  <li class="fragment" data-fragment-index="2">
    <a href="https://add0n.com/stylus.html">Stylus</a>
    (Jan 2017)
  </li>
  <li class="fragment" data-fragment-index="3">
    <a href="https://github.com/FirefoxBar/xStyle">xStyle</a>
    (Feb 2017)
  </li>
  <li class="fragment" data-fragment-index="4">
    <a href="https://cascadea.app/">Cascadea</a>
    (Safari only; Oct 2018)
  </li>
  <li class="fragment" data-fragment-index="5">
    <a href="https://add0n.com/stylus.html">Stylus</a>
    (Webkit-based Edge, through Chrome web store)
  </li>
</ul>

Note: Stylish sold to SimilarWeb Jan 2017

---

### UserStyle Storehouses

<ul>
  <li>
    <a href="https://userstyles.org">
      <span class="fragment highlight-red line-through" data-fragment-index="1">Userstyles.org</span>
    </a>
    <span class="fragment" data-fragment-index="1">(poorly maintained)</span>
  </li>
  <li><a href="https://33kk.github.io/uso-archive/">USO-archive</a> (archive of Userstyles.org)</li>
  <li><a href="https://freestyler.ws/">FreeStyler.ws</a></li>
  <li>Anywhere (UserCSS only)</li>
</ul>

Note: userstyles.org by Stylish author, also sold to SimilarWeb Jan 2017

---

![](https://raw.githubusercontent.com/Mottie/Presentations/master/customizing-the-web/images/nyan-cat-progress.gif)

<small>https://33kk.github.io/uso-archive/?style=95033</small>

---

## UserScripts

- What? Injected JavaScript
- Why? Change stuff
- How? UserScript manager

---

#### UserScript (JavaScript)

```js
// ==UserScript==
// @name        My Userscript
// @version     0.0.1
// @description Try to take over the world!
// @namespace   github.com/me
// @author      Me
// @match       https://www.google.com
// @grant       none
// ==/UserScript==
(function() {
  'use strict';
  // Your code here...
})();
```

---

### GitHub Custom Navigation

![](https://raw.githubusercontent.com/Mottie/Presentations/master/customizing-the-web/images/custom-nav-before.png)
![](https://raw.githubusercontent.com/Mottie/Presentations/master/customizing-the-web/images/custom-nav-after.png)
<img src="https://raw.githubusercontent.com/Mottie/Presentations/master/customizing-the-web/images/custom-nav-settings.png" style="height: 250px;" />

<small>https://greasyfork.org/en/scripts/20830</small>

---

#### More GitHub UserScripts

<div class="flex-row">
  <div>
    Before
    <img src="https://raw.githubusercontent.com/Mottie/Presentations/master/customizing-the-web/images/userscript1-before.png">
  </div>
  <div>
    After
    <img src="https://raw.githubusercontent.com/Mottie/Presentations/master/customizing-the-web/images/userscript1-after.png">
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

### UserScript Managers

![](https://raw.githubusercontent.com/Mottie/Presentations/master/customizing-the-web/images/userscript-support.png)

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


Note: GreasyFork.org also by Stylish author, not sold

---

### Quick Review

1. Install manager.
2. Go to a storehouse.
3. Search by site name.

---

#### UserStyle

![](https://raw.githubusercontent.com/Mottie/Presentations/master/customizing-the-web/images/stylus.gif)

---

#### UserScript

![](https://raw.githubusercontent.com/Mottie/Presentations/master/customizing-the-web/images/tampermonkey.gif)

---

### Thanks!

#### Rob Garrison

![](https://raw.githubusercontent.com/Mottie/Presentations/master/customizing-the-web/images/avatar.png)

&#x00ab;w&#x006f;wm&#111;&#x0074;&#116;y&#x40;&#103;m&#x0061;il&#46;c&#111;m&#187;
<br>
[github.com/Mottie](https://github.com/Mottie)
