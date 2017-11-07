---
title: "How to include intro module into your website"
date: 2017-11-06
tags: ["Developer", "Design", "Intro" , "User Experience"]
draft: false
---


#### Have you ever wondered how you can explain about your website to the users?
If you have complicated UI or if there are lots of things to do in your webpage
then, there is possibility that user might get lost.

## Best method to tackle this is to include simple intro tour which can guide users

### Are you wondering how

Ok let’s begin,

<p data-intro="How you can do this">You can achieve this by Intro.js</p>

Intro.js is open-source and free to use.
It is an javascript library to provide your website a simple
intro functionality.

### Benefits of Intro.js:


<ul data-intro="Benefits of Intro.js">
<li><code>Minified version of javascript and css file</code></li>
<li><code>User can navigate with arrow keys and mouse as well</code></li>
<li><code>Works on all browser</code></li>
<li><code>You can customize theme</code></li>
<li><code>You can control its behaviour</code></li>
</ul>

<h3 id="how-to-get-started">How to get started</h3>

Setting up Intro.js is not a hard task, that's the reason I pick this up
for my web projects.

Include the following css stylesheets in head tag of your website 

<pre data-intro="Include this in head tag of website"><code class="hljs xml"><span class="hljs-tag">&lt;<span class="hljs-name">link</span> <span class="hljs-attr">rel</span>=<span class="hljs-string">"stylesheet"</span> <span class="hljs-attr">href</span>=<span class="hljs-string">"https://cdnjs.cloudflare.com/ajax/libs/intro.js/2.7.0/introjs-rtl.css"</span>&gt;</span>
<span class="hljs-tag">&lt;<span class="hljs-name">link</span> <span class="hljs-attr">rel</span>=<span class="hljs-string">"stylesheet"</span> <span class="hljs-attr">href</span>=<span class="hljs-string">"https://cdnjs.cloudflare.com/ajax/libs/intro.js/2.7.0/introjs.css"</span>&gt;</span>
</code></pre>

After linking the css stylesheets, now you have to include the intro.js javascript
library in your website.

Include the following script in your website, right before closing the body tag.

<pre data-intro="Include this script before closing body tag"><code class="hljs xml"><span class="hljs-tag">&lt;<span class="hljs-name">script</span>  <span class="hljs-attr">src</span>=<span class="hljs-string">"https://cdnjs.cloudflare.com/ajax/libs/intro.js/2.7.0/intro.js"</span>&gt;</span><span class="undefined"></span><span class="hljs-tag">&lt;/<span class="hljs-name">script</span>&gt;</span>
</code></pre>



Now you are all set to use Intro.js in your website.

Lets talk about its usage now.

### Add data-intro to the HTML elements which you want to introduce.

data-intro is the explanation which you want to show in the popup explaining the
element in detail.

<pre data-intro="Call this function to start Intro"><code class="hljs css"><span class="hljs-selector-tag">introJs</span>()<span class="hljs-selector-class">.start</span>();
</code></pre>


You can also start an intro in particular class by doing this

<pre data-intro="Call intro for elements with a class"><code class="hljs css"><span class="hljs-selector-tag">introJs</span>("<span class="hljs-selector-class">.intro-this</span>")<span class="hljs-selector-class">.start</span>();
</code></pre>

By following steps defined in this article, you will be able to include 
simple intro module in your website.

As per my experience, I had to change some CSS according to my needs.
There is possibility that CSS of your website may collide with the intro.css
which can cause in messy layout of popup,
you can easily resolve that by inspecting the HTML in chrome.

<div class="btn btn-primary" onclick="startIntro()">Start Demo Now</div>

### If you find this useful, don’t forget to leave a comment.

<h2 id="enjoy-cheers" data-intro="You are all ready to go!">Enjoy, cheers !!.</h2>


