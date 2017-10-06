---
title: "Quick guide to integrate simple Image Cropping tool into website (For beginners)"
date: 2017-10-05
tags: ["Developer", "Image Cropping", "Website" , "Beginner"]
draft: false
---


### As a beginner, while developing a website usually people get stuck when they need to include module for profile picture upload.

There are many tools available around web which are free to use for cropping images. But the major challenges for beginner are :

* ```Which tool to use?```
* ```How to include it in website?```
* ```How to save image in server folder after cropping?```
* ```How to make your module responsive? So that it works on all screen sizes```

### If you are having the above questions in your mind, then you are right place!!
I started coding few years back, I found answers to my questions/problems myself but there was time when I used to stuck at a problem for days.
When I was working for a school project, there was a need to include profile picture upload module which took me a week to get it done.
I wrote this blog post so that it could help other beginners to workout the thing within an hour.

### The simplest tool I found for image cropping is:

*	```Croppie``` 


Lets begin with croppie

# Croppie

Croppie is one of the simplest, easy to intergrate and completely based on javascript. It provides you zooming capability and works well on all browsers and screen sizes. You can customize its css and make it responsive.

You can easily use croppie by including its css and javascript file.

```For getting started, include the css in header.```

```
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/croppie/2.5.0/croppie.css" />
```

```Include javascript before closing the body tag. ```

```
<script src="https://cdnjs.cloudflare.com/ajax/libs/croppie/2.5.0/croppie.js"></script>
```
We include javascript before closing tag because it makes sure all of the dom elements are loaded first before the execution of javascript functions.

```Then you just need to call croppie() for the object you want, such as image.```

```
<script>

var mycroppiedemo = $('.my-croppie').croppie({ 
    enableExif: false,
    showZoomer: true,
    enforceBoundary:true,
    boundary: {
      width: 400,
      height: 400
    },
    viewport:{
    	width:300,
    	height:300,
    	type:'square'
    }
  });
</script>
```

There are many parameters available such as:

* ```boundary``` is the outer container.
* ```customClass``` is the class which you can give to container to make it responsive.
* ```enableZoom``` allows you to zoom in and out.
* ```viewport``` is the inner container.


``` For saving the image you need to use the croppie result function on crop button click.
You can pass the type,size,format,quality of the cropped image ```

You can use the following code:

```
<script>
$( "#crop" ).click(function() {
  mycroppiedemo.croppie('result', {
            type: 'canvas',
            size: { width: 300, height: 300 }
        }).then(function(croppedImage) {
  	document.getElementById('croppedimg').setAttribute( 'src',croppedImage);
});
});
</script>
```

Here ```croppedImage``` is the base64 form of data.
Which you can easily convert and save at your server folder by any language, I have used c# for that.

```
public bool SaveImage(string ImgStr, string ImgName)
{   //Here you can replace ImgStr with croppedImage
    String path = HttpContext.Current.Server.MapPath("~/ImageFolder"); 


    //Check if directory exist
    if (!System.IO.Directory.Exists(path))
    {
    	//Create directory if it doesn't exist
        System.IO.Directory.CreateDirectory(path); 

    }

    string imageName = ImgName + ".jpg";

    //set the image path
    string imgPath = Path.Combine(path, imageName);

    byte[] imageBytes = Convert.FromBase64String(ImgStr);

    File.WriteAllBytes(imgPath, imageBytes);

    return true;
}
```



### Below is the working example for cropping image
<br><br>
<div>
<img class="my-croppie"  src="/images/croppie.jpg" />
</div>
<div style="text-align: center;">
<button id="cropnow1">Crop Now</button>
<br><br>
<div id="cropped1" style="width:100%; text-align:center; display: none;">
	<div><h3>Cropped Image:</h3></div>
<img id="croppedimg1">
</div>
</div>