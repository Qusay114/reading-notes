# Images :
In Html we can add images using img tag :

Example :

	<img src="cat.pmg" />

and we can resize the image using css style properties width and height 

Example :

	img
	{
		width:50%;
		height:50%;
	}

we can also add the image as a background for the elements

Example :

	body
	{
		background-image:url("cat.png")
	}



# Search Engine Optimization (SEO) :
Search engine optimization helps visitors find your
sites when using search engines , Analytics tools such as Google Analytics allow you to
see how many people visit your site, how they find it,
and what they do when they get there.To put your site on the web, you will need to obtain a
domain name and web hosting.
FTP programs allow you to transfer files from your
local computer to your web server.
Many companies provide platforms for blogging, email
newsletters, e-commerce and other popular website
tools (to save you writing them from scratch).



# Video :

To show a video in HTML, use the video element.

Example :

	<video width="320" height="240" controls>
    <source src="movie.mp4" type="video/mp4">
    <source src="movie.ogg" type="video/ogg">
    Your browser does not support the video tag.
    </video>

The controls attribute adds video controls, like play, pause, and volume.

It is a good idea to always include width and height attributes. If height and width are not set, the page might flicker while the video loads.

The <source> element allows you to specify alternative video files which the browser may choose from. The browser will use the first recognized format.

The text between the <video> and </video> tags will only be displayed in browsers that do not support the <video> element.

To start a video automatically, use the autoplay attribute:

	
	<video width="320" height="240" autoplay>
    <source src="movie.mp4" type="video/mp4">
    <source src="movie.ogg" type="video/ogg">
    Your browser does not support the video tag.
     </video>
