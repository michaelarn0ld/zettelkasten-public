# HTML Media Elements

## Formats
* Best for images are: PNG, SVG, JPEG, GIF
* Best for video is: OGG, WebM, MP4
* Best for audio is: WAV, OGG, MP3, MP4


## The <img> Element
Quick tips:
* Using an inline ```style=""``` attribute is considered a good practice when
adjusting the szie of an img element
* There is no closing tag for this element

If you want to split a single image into multiple clickable regions; you may do
so by defining a ```<map>``` element with child ```<area>``` elements associated
with the usemap attribute of the ```<img>``` element. Consider a map of North
America and you wanted all three countries to be clickable:
```html
 <img src="north-america.png" width="300" height="300" alt="Clickable map of North America" usemap="#na-map">

<map name="na-map">
  <area shape="rect" coords="0,0,300,100" href="canada.html" alt="Sun">
  <area shape="rect" coords="0,100,300,200" href="usa.html" alt="Mercury">
  <area shape="rect" coords="0,200,300,300" href="mexico.html" alt="Venus">
</map>
```


## The <video> element
Quick usage to embed a video:
```html
<video src="videos/hello.mp4" type="video/mp4" controls>
   <p>This element only shows up if the browser does not support HTML5 video. Use it to provide a download link or alternate instructions.</p>
</video>
```
 Note that the controls attribute instructs the browser to add its basic video
 controls; JS libraries can be used to modify the defaults.

 You can also specify multiple sources for a video in situations where you need
 to support older versions of browsers or a mixture of mobile devices:
 ```html
 <video controls>
    <source src="videos/hello.mp4" type="video/mp4">
    <source src="videos/hello.webm" type="video/webm">
    <p>This element only shows up if the browser does not support HTML5 video. Use it to provide a download link or alternate instructions.</p>
</video>
```

Other common video attributes includes:
* width= and height=
* autoplay
* loop
* muted
* poster= (provide the image path to an image you want to display before the vid
is played)


## The <track> Element
For hearing impaired users, you can add test tracks to videos with a format 
called WebVTT which combines text to be displayed with times in the video
player:
```html
<video controls width="800" height="600"
       autoplay loop muted
       poster="images/hello-the-movie.png">
    <source src="videos/hello.mp4" type="video/mp4">
    <source src="videos/hello.webm" type="video/webm">
    <track kind="subtitles" src="videos/hello_en.vtt" srclang="en">
    <p>This element only shows up if the browser does not support HTML5 video. Use it to provide a download link or alternate instructions.</p>
</video>
```
Tracks can specify a language; you can add multiple tracks to support multiple
languages. Search  engines can index the track file which can lead to search
links directly to your videos based on the content.


## The <audio> Element
Here is an example of the audio element:
```html
<audio controls>
    <source src="audio/hello.mp3" type="audio/mp3">
    <source src="audio/hello.wav" type="audio/wav">
    <p>This element only shows up if the browser does not support HTML5 video. Use it to provide a download link or alternate instructions.</p>
</audio>
```


## Related
[202110210320](../202110210320) - Semantic HTML Block Elements
[202110210421](../202110210421) - Interesting Details of Inline HTML Elements
[202110210445](../202110210445) - HTML Head Elements
[202110210536](../202110210536) - HTML Tables: Quick Tips


## Tags
#webdev
