# Class 14a - CSS Transforms, Transitions, and Animations

[<== Main Page](../README.md)

## [What Google Learned From Its Quest to Build the Perfect Team](https://www.nytimes.com/2016/02/28/magazine/what-google-learned-from-its-quest-to-build-the-perfect-team.html)

Project Aristotle showed that groups need to have somewhat equal talking time and form norms to behave in a more cohesive manner. No one wants to put on their workface when they come to groups.

## [Transforms](https://learn.shayhowe.com/advanced-html-css/css-transforms/)

- Transform available in 2D and 3D versions.
  - Should incude vendor prefixes to allow for discrepancies within browsers

- 2D Rotate positive 0 to 360 can rotate clockwise and negative counter.

```render-html
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
```

```render-css
.box-1 {
  transform: rotate(20deg);
}

.box-2 {
  transform: rotate(-55deg);
}
```

- 2D Scale changes the apparant size of the element.  .01 to .99 makes it smaller and greater than 1.01 makes it larger.

```render-html
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
```

```render-css
.box-1 {
  transform: scale(.75);
}
.box-2 {
  transform: scale(1.25);
}
```

- Can scale just the x or y axis values

```render-html
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
<figure class="box-3">Box 3</figure>
```

```render-css
.box-1 {
  transform: scaleX(.5);
}
.box-2 {
  transform: scaleY(1.15);
}
.box-3 {
  transform: scale(.5, 1.15);
}
```

- 2d Translate works like relative positioning by oushing and pulling the the element in different directions.

```render-html
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
<figure class="box-3">Box 3</figure>
```

```render-css
.box-1 {
  transform: translateX(-10px);
}
.box-2 {
  transform: translateY(25%);
}
.box-3 {
  transform: translate(-10px, 25%);
}
```

- 2D Skew distorts images on their horizontal or vertical axis or both.

```render-html
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
<figure class="box-3">Box 3</figure>
```

```render-css
.box-1 {
  transform: skewX(5deg);
}
.box-2 {
  transform: skewY(-20deg);
}
.box-3 {
  transform: skew(5deg, -20deg);
}
```

- Combining transforms

```render-html
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
```

```render-css
.box-1 {
  transform: rotate(25deg) scale(.75);
}
.box-2 {
  transform: skew(10deg, 20deg) translateX(20px);
}
```

- 2D Cube

```render-html
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
<figure class="box-3">Box 3</figure>
<figure class="box-4">Box 3</figure>
```

```render-css
.box-1 {
  transform: rotate(15deg);
  transform-origin: 0 0;
}
.box-2 {
  transform: scale(.5);
  transform-origin: 100% 100%;
}
.box-3 {
  transform: skewX(20deg);
  transform-origin: top left;
}
.box-4 {
  transform: scale(.75) translate(-10px, -10px);
  transform-origin: 20px 50px;
}
```

## [Transitions & Animations](https://learn.shayhowe.com/advanced-html-css/transitions-animations/)

## [8 SIMPLE CSS3 TRANSITIONS THAT WILL WOW YOUR USERS](https://www.webdesignerdepot.com/2014/05/8-simple-css3-transitions-that-will-wow-your-users)

## [Pure CSS Bounce Animation](https://codepen.io/dp_lewis/pen/gCfBv)
