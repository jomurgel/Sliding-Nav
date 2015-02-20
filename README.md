# Slide Nav
An IE7+ compatible (tested) jQuery, HTML and CSS full-width sliding navigation.
[View Demo](https://github.com/jomurgel/Sliding-Nav)

## Features
- Lightweight
- IE7+ Compatible
- Mobile compatible
- Desktop and mobile browser compatible
- Toggle Menu Language
- Fluid responsive

## Setup
Simple complication with [Gulp](http://gulpjs.com/).

```
npm install gulp
npm install gulp-sass
```

## HTML

```html
&lt;a href="#" id="toggle"&gt;Open&lt;/a&gt;<br/>

&lt;div id="wrap"&gt; CONTENT HERE &lt;/div&gt;<br/>

&lt;nav class="nav"&gt;
	&lt;ul&gt;
		&lt;li&gt;&lt;a href=""&gt;Nav Item&lt;/a&gt;&lt;/li&gt;
	&lt;/ul&gt;
&lt;/nav&gt;
```

## The jQuery

```javascript
$(document).ready(function() {
	$('#toggle').on('click', function() {
	    // add class to show nav
	    $('.nav').toggleClass('show');
	    
	    // add class to push content without squishing it
		$('#wrap').toggleClass('push');
		
		// toggle class of button
		$(this).toggleClass('open');
		
			// toggle button text
			if ($(this).text() == "Open") {
	        	$(this).text("Close");
	        }
	        else {
	       	 $(this).text("Open");
	        }
	  	return false;
	});
});
```

## The SCSS

```css
// Page Wrapper
#wrap {
	width: 96%; // important to maintain 100% width so content doesn't squish
	padding: 2%;
}

// Navigation Styles
.nav {
    position: fixed; // important
    top: 0;
    left: -250px; // increase negative px for delay
    height: 100%;
    z-index: 999999;
    width: 250px; // width of navbar
}

// Events
.push {
	margin-left: 250px; // move wrap right;
}

.show {
	left: 0; // move navbar right
}
```
	
## License
Released under the [MIT License](LICENSE).  Made by [jomurgel](https://github.com/jomurgel).