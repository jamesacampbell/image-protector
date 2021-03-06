author: James Campbell 
creation date: July 2013


### Congratulations on wanting to protect your images online 

The goal of this project is to make it as easy as possible to _somewhat_ protect the images on your website. *If you really don't want people to steal your images, don't post them on the web.* That being said, let's move on:

There are a few things you need access to:

1. Your server where your domain is hosted. 
You need to be able to upload files to your server. There are workarounds for this but to make it as easy as possible server access is required
2. Your stylesheet for your site (example: styles.css).
3. Devices and browsers to test functionality and that everything is working properly.


### Initial setup

I include an example html file to get you started. The file is labeled 'example.html' so you can't miss it.
You will notice that everything works with a div wrapped around an img tag with a class of 'protected' and 'unprotected' which are referenced in the separate style.css file and include the specific media targeting for mobile devices to disallow touch events on images.

View the page on [my codepen](http://codepen.io/jamesacampbell/pen/bdBeaq) as a live working demo version of this example.

### Disabling right-clicking on images (img)

This is a simple snippet of javascript. I use jquery for brevity in the example.js file. It turns off right clicking of any img tage with class named 'protected'. 

Here is the code:
	
	<script type="text/javascript">
	function NoClick() {
	$('body').on('contextmenu', '.protected', function(e){ return false; }); 
	}
	</script>

### Disabling long-touch menu on images (which allows saving) on mobile

This is a little more involved because you need separate functions for android, firefox's mobile browser, and apple devices.
The code for apple devices is easiest to implement, there is no javascript required, just add 

	-webkit-touch-callout: none;

to your CSS media queries. Refer to the style.css example for details.

### CSS suggested callout

Here is the example version css:
```
.protected {
 -webkit-touch-callout: none;
}
```

So you just need to reference or include this javascript in any page that you want to protect and then update your img tag with <code>class='protected'</code> and everything should work properly assuming you updated your stylesheet (css) properly with the .protected class in place.
