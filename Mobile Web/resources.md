# Resources

* [Brad Frost responsive pattern library](http://bradfrost.github.io/this-is-responsive/patterns.html)
* [BBC Responsive News](http://responsivenews.co.uk/)

## Process and Workflow

* [Content Structure - Source Order](https://vimeo.com/89535832)
* [A matter of workflow - Nathan Ford](http://www.iaskyouanswer.co.uk/nathan-ford.php)

> You can't design a good layout if you don't know the content.

> Introducing new layouts for screen sizes where the content loses it's integrity.

> An early trap for us that I see many other falling into is the idea of "screen size" targeting. Setting breakpoints before you build can lead to some real pain when trying to squeeze in content later.



## Responsive Typography

* [FitText](http://fittextjs.com/)

## Media Queries

Style sheets with media queries attached to their `<link>` tags will still download even if it evaluate to `false`.

* [Good resource for knowing the logical operators of media queries](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Media_queries)

## Meta Viewport

* [Opera's introduction to meta viewport](http://dev.opera.com/articles/view/an-introduction-to-meta-viewport-and-viewport/)

## Retina

* [Retina for web workflow](http://michieldegraaf.com/post/retina-for-web-workflow/)
* [Optimizing graphics for retina display](http://www.studiopress.com/design/css-background-size-graphics.htm)
* [WWDC - Delivering web content on high resolution displays](https://developer.apple.com/videos/wwdc/2012/?id=602)

```
.logo {
  width: 200px;
  height: 60px;
  background-image: url(logo.png) no-repeat;
  background-size: 100% 100%;
  
  // Or half it
  background-size: 100px 100px, 100% 100%;
}

@media only screen and (-webkit-min-device-pixel-ratio: 2) {
  .logo {
    background-image: url(logo@2x.png) no-repeat;
    
    // Or half it
    background-size: 50px 50px;
  }
}
```

Notice the `background-size` is set to `100%` for both width and height. This makes it easier to change our real `width` and `height`.

```
@media (min--moz-device-pixel-ratio: 1.5),
       (-o-min-device-pixel-ratio: 3/2),
       (-webkit-min-device-pixel-ratio: 1.5),
       (min-resolution: 1.5dppx) {
}
```

## Favicon

16px for standard screens and 32px for retina screens.

* [Retina version](http://xiconeditor.com/)