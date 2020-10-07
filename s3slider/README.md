# s3Slider, slick jQuery slideshow plugin

## About
The s3Slider jQuery plugin is made by example of [jd's smooth slide show script](http://smoothslideshow.jondesign.net/timed.html). I needed something like that for jQuery (for my web site [kruskica.net](http://www.kruskica.net)). Since i didn't find it after a small research i decided to build it by my self.

## How to use
It is very easy. First include the jQuery library then include the s3Slider javascript in the head of the page(s) where you want to use s3Slider.

jQuery can be download from [jQuery homepage](http://docs.jquery.com/Downloading_jQuery).
```html
<script src="js/jquery.js" type="text/javascript"></script>
<script src="js/s3Slider.js" type="text/javascript"></script>
```
*Important*: For the script to work properly there is a set of rules that must be followed.

### HTML
```html
<div id="s3slider">
    <ul id="s3sliderContent">
        <li class="s3sliderImage">
            <img src="#">
            <span>Your text comes here</span>
        </li>
        <li class="s3sliderImage">
            <img src="#">
            <span>Your text comes here</span>
        </li>
        <div class="clear s3sliderImage"></div>
    </ul>
</div>
```

#### Explanation
If you set that main div id is `s3slider` as we did here, that is the name that must be prefix for all other classes and id's for that specific gallery (slide show). For example, if you set an id for main div as `your_name`, the inner id must be `your_nameContent` and the class ``.your_nameImage` like in example above.

The second thing is that every `.your_nameImage` element in it self must have span. Also, the last div with class clear must also have an class of image holder in this case `.your_nameImage`. if you don't put that, the last image will *NOT* be shown in the slide show.

### CSS
```css
#s3slider {
    width: 400px; /* important to be same as image width */
    height: 300px; /* important to be same as image height */
    position: relative; /* important */
    overflow: hidden; /* important */
}

#s3sliderContent {
    width: 400px; /* important to be same as image width or wider */
    position: absolute; /* important */
    top: 0; /* important */
    margin-left: 0; /* important */
}

.s3sliderImage {
    float: left; /* important */
    position: relative; /* important */
    display: none; /* important */
}

.s3sliderImage span {
    position: absolute; /* important */
    left: 0;
    font: 10px/15px Arial, Helvetica, sans-serif;
    padding: 10px 13px;
    width: 374px;
    background-color: #000;
    filter: alpha(opacity=70); /* here you can set the opacity of box with text */
    -moz-opacity: 0.7; /* here you can set the opacity of box with text */
    -khtml-opacity: 0.7; /* here you can set the opacity of box with text */
    opacity: 0.7; /* here you can set the opacity of box with text */
    color: #fff;
    display: none; /* important */
    top: 0; /*
        if you put top: 0;  -> the box with text will be shown
                                at the top of the image
        if you put bottom: 0;  -> the box with text will be shown
                                at the bottom of the image
    */
}

.clear {
    clear: both;
}
```

Then you need to initialize s3Slider and set the duration of how long will one picture be shown on the page (value is in miliseconds).

### JS
```javascript
$(document).ready(function() {
    $('#s3slider').s3Slider({
        timeOut: 4000
    });
});
```

### Browser support
This plugin has been tested and is known to work in the following browsers:

 * Firefox 2.x (Win)
 * Firefox 3.x (Win/Linux/Mac)
 * Opera 9.6 (Win/Linux)
 * Safari 3.0.3 (Win/Mac)
 * Internet Explorer 6 (Win)
 * Internet Explorer 7 (Win)
 * Google Chrome (Win)

---
Boban Karišik, sometime in 2008.
