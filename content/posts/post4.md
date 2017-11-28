---
title: "How to show time as x-minute ago in your website"
date: 2017-11-28
tags: ["Developer", "Design", "Time" , "Javascript"]
draft: false
---


#### Have you ever wondered how to show time as ```x-minute ago``` in your website?
Displaying date as ```DD/MM/YYYY hh:mm:ss``` is very common, but due the frequency of content posted
on your website there could be a need to show time as x-minutes ago.

## Best method to this by using simple javascript libraries, which saves you a lot of server side coding.

### Are you wondering how

Ok let’s begin,

You can achieve this by ```moment.js and livestamp.js```, off course you need ``jquery`` too!

moment.js is open-source and free to use.
It is a lightweight JavaScript date library for parsing, validating, manipulating, and formatting dates.

### Benefits of moment.js:


<ul >
<li><code>It is minified, very small in size</code></li>
<li><code>Has variety of options to parse and validate datetime.</code></li>
<li><code>Works on all browser</code></li>
<li><code>You can easily set it up in node.js, NuGet</code></li>
<li><code>You can easily manipulate its behaviour</code></li>
</ul>


Livestamp.js is a simple plugin that provides auto-updating timeago text to your timestamped HTML elements using Moment.js

### Benefits of livestamp.js:


<ul >
<li><code>Just as moment, it is also minified, and very small in size</code></li>
<li><code>It updates itself as time goes by</code></li>
<li><code>No extra javascript or HTML required</code></li>
<li><code>It can also parse future dates like "in 30 minutes"</code></li>
<li><code>You can control its trigger event</code></li>
</ul>

<h3 id="how-to-get-started">How to get started</h3>

Setting up this functionality is not very hard, that's why I recommend 
using this in your projects.

Include the following script before the closing tag of your website 

```
<script src="https://code.jquery.com/jquery-3.2.1.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.19.2/moment.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/livestamp/1.1.2/livestamp.min.js"></script>
```


Now you are almost there to show date time as x-minute ago in your website.

Lets talk about its usage now.

### Add data-livestamp to the HTML element in which you want to show datetime.

I would recommend using ```<span>``` because its a inline tag.

### Remember that you have to keep this tag empty, otherwise its content would be replaced 
by something like 'x-time ago'

# Few examples:

### Current datetime example:
```
<span id="datetimenw"></span>
<script>
$('#datetimenw').attr('data-livestamp', new Date().toLocaleString());
</script>
```
Output : <span id="datetimenw"></span>

### Past datetime example:
```
<span data-livestamp="11/28/2017, 11:55:55 AM"></span>
```
Output : <span data-livestamp="11/28/2017, 11:55:55 AM"></span>

### Future date example:
```
<span data-livestamp="12/20/2017, 11:55:55 AM"></span>
```
Output : <span data-livestamp="12/20/2017, 11:55:55 AM"></span>

# Available Events

```change.livestamp``` event is available for your use, which is triggered right before
the time is updated.

Let's see a basic usage of this event.

```
<span id="eventExample"></span>
<script src="https://cdnjs.cloudflare.com/ajax/libs/notify/0.4.2/notify.min.js"></script>
<script>
  $('#eventExample').on('change.livestamp', function() {
   $.notify("Time Updated", "success");
  }).livestamp();
</script>
```
### You will see notification on top right of webpage everytime when this time changes: 
## <span id="eventExample"></span>


<br><br>
By following steps defined in this article, you will be able to include 
x-minute ago functionality in your website.

### If you find this useful, don’t forget to leave a comment, or start new thread for any help regarding setting up this thing in your website.

<h2 id="enjoy-cheers" data-intro="You are all ready to go!">Enjoy, cheers !!.</h2>


