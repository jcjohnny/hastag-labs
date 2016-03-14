*HASHTAG LABS developer quiz*

###### INSTRUCTIONS
Please complete the following questions / exercises. Some of the points are interesting and you could write a lot about them. Don’t worry about that! We’re not particularly concerned about the nuances or terminological perfection just give 1 - 2 sentences that hit the main idea. We’d prefer that you guess rather than look things up, but if you do look things up, please tell us where you looked. This should take 10 - 30 minutes.

##### QUESTIONS

1. What is the difference between HTTP and HTTPS?

    ``` The difference lies in the letter S which stands for Secure. Typically, an SSL certificate is needed to maintain an HTTPS secure connection and are usually required for companies accepting online payments operating in e-commerce.```
2. What is the difference between HTTP GET and POST?

    ``` HTTP GET requests data from a server. HTTP POST submits data to the server.```
3. What is the difference between the HTTP 2xx status codes and 4xx status codes?

    ``` HTTP 2xx status means there’s a successful connection to the server. 4xx status codes means there’s a problem with the user’s connection to the server. ```
4. What is Ajax (conceptually, what does it do)? Describe a situation where it is useful.

    ``` Ajax can make changes to a web page without having to reload the page. It is typically useful when content on page is being changed or updated while the user is viewing a page. Online forms are a situation where Ajax is the most useful – as it can update and inform as a user is typing. Having to submit a form only to be told that it is filled incorrectly is slow and non user-friendly. ```
5. What is responsive design?

    ``` Responsive design is when a website is built for most or all screen sizes to optimize readability and performance. ```
6. What is the difference between these 3 CSS rules?
```css
div {background:#fff;}
/* changes the background color of all HTML div tags*/
```
```css
#div {background:#fff;}
/* changes the background color of only one HTML tag with the id name of div.*/
```
```css
.div {background:#fff;}
/* changes the background color of all HTML tags with the class name of div.  */
```

7. What is the difference between these 2 uses of the ```<script>``` tag?
```html
<script src=http://example.com/whatever.js></script>
<!-- Fetches and uses an external JavaScript file from an online source -->
```
```html
<script> var whatever = true </script>
<!-- Hardcoded script written and executed from within HTML code. -->
```
8. What is the difference between these two javascript snippets?
```javascript
var x = function() { return 1+1; }();
// Names and executes the function. Can be used again later in the script.
```
```javascript
var y = function() { return 1+1; };
// Names the function and saves it until it is called.
```

##### PRACTICAL
1. Write HTML/CSS to draw the following scene (inline css is fine if you want):
    * One red box, 200x200 pixels
    * One blue box, 200x200 pixels
    * One green box, 100x100 pixels
    * The green box should be centered inside the red box
    * The red and blue boxes should not overlap
```html
<div id="reddy" style="width: 200px; height: 200px; background-color: red; position: relative;"><div id="greeny" style="width: 100px; height: 100px; background-color: green; left: 50px; top: 50px; position: relative;"></div></div>
<div id="bluebeans" style="width: 200px; height: 200px; background-color: blue;"></div>
```
2. You have started an analytics company with the domain “hashtag¬analytics.com”. You provide this tracking pixel for your customers to place on their websites. By summing the number of times the pixel was loaded, you calculate the number of visitors to each site.

    ```<img src=http://hashtag-analytics.com/12345/pixel.gif width=”1” height=”1”/>```

    As it stands, this pixel has a problem because it will be cached by the browser.
    * Why is caching a problem for the analytics company?

    ``` Data and information gets updated. The tracking pixel can remain un-updated while the sites contents change and its viewer’s behaviors can change. ```
    * How could you prevent browser caching? (use any technique(s) you want)

    ``` There are a lot of answers from http://stackoverflow.com/a/2068407. The most frequented answer that I came across was to use HTML meta tags in the header ```
	```html
    <meta http-equiv="Cache-Control" content="no-cache, no-store, must-revalidate" />
	<meta http-equiv="Pragma" content="no-cache" />
	<meta http-equiv="Expires" content="0" />
    ```
    * What will happen if the customer’s website is served over HTTPS? How could you modify the tracking pixel to fix that?

    ``` From my experience in working with SSL certificates, I’ve found that links that lead to other sites, especially image links from an online source without HTTPS will result in a none secure greyed lock stating that it had some unsecure connections. An answer from http://preview.tinyurl.com/hampv22 suggested that modifying the link itself by omitting the http (//hashtagh-analytics.com/...) portion of the link can fix that issue ```
    * List some information the tracking company could collect (ex: IP address)

    ``` Type of browser used, Pageviews. Amount of visitors who visit. Amount of times an email was opened ```
    * List some additional information (if any) that could be collected if a ```<script>``` tag is used instead of an ```<img>``` tag.
    ``` Screen Resolution. Plugins used. Website Activity. ```

3. Harder! The following image tag appears somewhere on some webpage. The rest of the page is valid HTML, but otherwise unknown.

    ```<img id=”myimage” src=http://hashtag-analytics.com/my/image.jpg width=”300 height=”250”/>```

    Write CODE in plain JavaScript to do the following (jQuery is fine too, if you prefer):
Every 2 seconds:
    * Check whether the image is viewable**
    * If yes, write “visible” to the console (that is, window.console)
    * If no, do nothing **
** the image is “viewable” if any part of it appears on the screen (so if the image is entirely above or below the viewport, then the user cannot see it, so it is not considered “viewable”). You can ignore horizontal bounds checking.

    ```
    There is a plugin for Jquery that does this quite well
    https://www.customd.com/articles/13/checking-if-an-element-is-visible-on-screen-using-jquery
    ```
    ```javascript
    window.setInterval(function() {
        if ($(‘#myimage’).visible()){
            if( window.console ) {
        	   console.log( “visible” );
            };
        };
    },2000);
    ```
