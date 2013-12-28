FreeStyle
=========

###What is it?
Think of FreeStyle as a 'lite' version of [ExtraContent](http://extracontent.info). It was invented to allow RapidWeaver users greater freedom to easily build attractive theme banners. It solves many of the problems previously inflicted by the use of fixed-size divisional containers and CSS background images for theme banners. Any content with an ID of **fs** applied is automatically appended to the banner region in the page. So FreeStyle has proven to be a simple yet reliable and highly effective method for customising and building theme banners.

---

###Theme developer guide
Almost any RapidWeaver theme can be made FreeStyle-compliant; within a matter of seconds and of no detriment to theme compatibility or reliability. This is code you can drop-in and forget about. Simply include this jQuery Javascript code immediately before or after your existing ExtraContent code:

	// FreeStyle banners
	$(document).ready(function(){
		$('#fs').appendTo('#freeStyle');                                           
	});
	
At the point in the page where you want people to embed their banners (like an existing theme header or banner container), enter this HTML code in the theme index.html file:

	<div id="freeStyle"></div>

Typically it is wise to put this code near an existing ExtraContent container, you might be using for banner content. Now any content in the page with an ID of **fs** applied will be embedded into the designated FreeStyle container.

As an optional extra, if you want FreeStyle content hidden until after it's been moved to the designated FreeStyle banner container, simply add this CSS code to your theme:

	#contentWrapper #fs,
	#sidebar #fs {
		display: none;
	}

Edit that CSS code to reference the ID's of your theme content container and sidebar. Now FreeStyle content will only get rendered in the designated banner, and will not flash about on the screen, while the page is still loading.

---

###Plugin / stack developer guide
Provide a setting in your addon which will enclose your content or apply an ID of **fs** to it, like this:

	<div id="fs">
		<!-- Your plugin or stack content is rendered in here -->
	</div>

You may need to update your support documentation to explain what this feature does and the need for a FreeStyle-compatible RapidWeaver theme.

---

###FreeStyle for end users
There are two main methods to take advantage of FreeStyle, in your FreeStyle enabled RapidWeaver themes:

####1) HTML code snippets:
The traditional method for getting FreeStyle banners setup (and arguably the quickest for regular static images) is to type the following HTML code into your page content or sidebar container:

	<div id='fs'></div>

Then enter a [standard HTML image tag](http://www.w3schools.com/html/html_images.asp), to pull your image in, like this:

	<div id='fs'><img src='http://example.com/images/tree.jpg' alt='My Image'/></div>

Images can be pulled in using the normal [RapidWeaver resource macro](http://realmacsoftware.freshdesk.com/support/articles/11330-how-to-use-rapidweaver-5-resources):

	<div id='fs'><img src='%resource(my-image.jpg)%' alt='My Image'/></div>

Or using the pathto macro for an image that is already stored in the theme contents (like one of the example banner images supplied with the theme):

	<div id='fs'><img src='%pathto(images/editable_images/1.jpg)%' alt='My Image'/></div>
	
In the above *pathto* example, incrementing the number of the image (e.g. 1.jpg), will change the image displayed. So 4.jpg would display a different image, depending on how your theme names and numbers example banner images. 

These code snippets can be saved in RapidWeaver for quick future use. The **alt=''** attribute you see in the image tag can be used to provide a description about your image to search engines and social media services. When a FreeStyle-enabled theme sees the **'fs'** code, it knows to treat that as content for the FreeStyle container. It's hoped that this new FreeStyle concept will give control of theme banners and headers back to theme users again, and help streamline developer workflows. Don't forget to take advantage of the free [FreeStyle stack](http://www.stacks4stacks.com/freestyle/) as well, for the Stacks plugin. 

Useful tip: if you are finding that your FreeStyle banner images are causing content to get shifted down the page as it loads, try providing a height and width attribute in the HTML image tag, set to the same width and height as your original image:

	<div id='fs'><img src='http://www.example.com/my-image.jpg' alt='My Image' width='1500' height='500'/></div>

All modern web browsers will then reserve a space (equal to the dimensions you specify) for the image to load in, which will reduce shifts occurring during and after page rendering. Quite a few web browsers will even go ahead and calculate responsive scaling, *before* the image has finished loading. So this can be a useful trick to know about.

####2) FreeStyle stack
This single stack element is intended for use with the Stacks plugin, developed by YourHead Software. It's a great stack to use if you're already making use of the Stacks plugin in your projects, and need a fast and easy stack to build FreeStyle banners with. The latest version available from the Stacks4Stacks website, and now supports the following content types:

- Blank (for custom content)
- Static image
- Splash
- Jumbotron
- BX Slider
- Google Maps
- Open Street Maps
- Dailymotion Video
- HTML5 Video
- Kickstarter Video
- TED Video
- Vimeo Video
- Vine Video
- YouTube Video

To use the FreeStyle stack, simply drag and drop a copy of it into your Stacks page. Following the instructions shown in edit mode, to setup your content The FreeStyle stack has **experimental support** for the PlusKit @import(()) feature and Joe Workman's 'Global Content' plugin, both of which are not included with the FreeStyle stack.

---

###Footnotes
FreeStyle is released under the open source MIT license. It can be used in almost any personal or commercial project, with few restrictions.

If you have any suggestions for features or future changes, please make use of the **Issues** button, on the FreeStyle Github page.

RapidWeaver is a registered trademark of Realmac Software LTD, Brighton, UK.