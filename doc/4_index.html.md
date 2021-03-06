[3. JavaScript Module][js-module] &nbsp;&lt;&nbsp; Previous Page

[js-module]: 3_script.js.md

# 4. HTML Page

To make [HyperText Slider][slider] work via [Node][node],
3 things are needed in client HTML.

[slider]: https://github.com/muroc/hyper-text-slider
[node]: https://nodejs.org/en/

```html
<!DOCTYPE html>
<html>
<head>
  <title>HyperText Slider via Node and Browserify</title>
//:: stylesheet :://
</head>
<body>
//:: slider-declaration :://
//:: browserified-script :://
</body>
</html>
```

## 4.1. Stylesheet

Styles for the slider should be linked in `<head>` section (see
[5. Stylesheet][stylesheet]). We also need to make `<html>` element invisible.
Using `opacity` for invisibility is the best choice because transition/animation
events can fire normally while contents being hidden. Also `opacity` is a
property that can be used in a CSS transition.

```html
//== stylesheet ==//

  <style type=text/css> html { opacity: 0; } </style>
  <link href=style.css rel=stylesheet>
```

## 4.2. Slider Declaration

Element with [`ht-slider`][layout-slider] class name signifies
declaration of a slider.
Features of HyperText Sliderare enabled by adding other class names on
the slider element.
[`ht-defaults`][ht-defaults] is an option group, which enables
most of the features.

This is a minimal configuration, but you can get pretty wild in here
(enable specific [options][option-classes],
set [CSS transitions][transition-class],
or specify [time duration][time-classes] of a slide).
Please consult [Declarative API of HyperText Slider][css-api] for details.

[layout-slider]: https://github.com/muroc/hyper-text-slider/blob/master/doc/class-names.md#ht-slider
[transition-class]: https://github.com/muroc/hyper-text-slider/blob/master/doc/class-names.md#ht-transition--sg
[time-classes]: https://github.com/muroc/hyper-text-slider/blob/master/doc/class-names.md#time-class-names
[option-classes]: https://github.com/muroc/hyper-text-slider/blob/master/doc/class-names.md#option-class-names
[ht-defaults]: https://github.com/muroc/hyper-text-slider/blob/master/doc/class-names.md#ht-defaults
[css-api]: https://github.com/muroc/hyper-text-slider/blob/master/doc/class-names.md

```html
//== slider-declaration ==//

  <div id=my-slider class="ht-slider ht-defaults ht-theme--black">
    <div id=webpage class="ht-theme--defaults">
      <p>This is a simple web page...
    </div>
    <div id=slideshow>
      <p>...which contains a nice
       <a href=https://github.com/muroc/hyper-text-slider>CSS3 Slideshow</a>.
    </div>
    <div id=dependencies>
      <p>It was built using
        <a href=https://github.com/gulpjs/gulp class=nth1>gulp</a>,
        <a href=https://github.com/substack/node-browserify class=nth2>browserify</a>,
        <a href=https://github.com/sass/sass class=nth3>sass</a>,
        and <a href=https://github.com/muroc/hyper-text-slider class=nth4>hyper-text-slider</a>.
    </div>
    <div id=more>
      <p>For more info, check out
       <a href=https://github.com/muroc/hyper-text-slider-node-tutorial>HyperText Slider Node Tutorial</a>.
    </div>
  </div>
```

Any direct child of the slider element is treated as a slide
(above code contains 4).
There are no constraints on the contents of&nbsp;a&nbsp;slide.
It can be anything that your target web browser understands
([HTML][html], [SVG][svg] or even [WebGL][webgl]).

[html]: https://www.w3.org/TR/html5/
[svg]: https://www.w3.org/TR/SVG2/
[webgl]: https://www.khronos.org/registry/webgl/specs/1.0/

## 4.3. Browserified Script

Lastly, at the very bottom of the page, we load our browserified script.

```html
//== browserified-script ==//

  <script src=script.js type=text/javascript>
  </script>
```

&nbsp;<br>
Next Page &nbsp;&gt;&nbsp; [5. Stylesheet][stylesheet]

[stylesheet]: 5_style.scss.md

