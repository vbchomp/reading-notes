# Class 05 - Images, Color, text

[<== Main Page](../README.md)

## *HTML Book* Chapter 5 - Images

- Should be relevant, informative, the right modd, recognizable, fit colors
- Stock photo websites, www.istockphoto.com, www.gettyimages.com, www.veer.com, www.sxc.hu, www.fotolia.com

```render-html
<img src="imageFileName or URL" alt="Description of image" title="Sentence on image" width="600" height="450"/>
```

- Place images before a paragraph, inside the start of a paragraph and in the middle of a paragraph
- Save images in the right format, right size and by pixels
- Editing tools online, www.photoshop.com, www.pixlr.com, www.splashup.com, www.ipiccy.com
  - SW, Adobe Fireworks, Pixelmator, PaintShop Pro, Paint.net
- JPEG should be used if pic has a lot of colors
- GIF or PNG used when large areas of same color or few color
- Make sure to choose portrait or landscape to make sense
- Measure using pixels
- Vector images are created with SW and are resolution independent
- Transparent GIF or PNG
- Figure and figure caption

```render-html
<figure>
  <img src="image.jpg" alt="Description" />
  <br/>
  <figcaption>Words to describe pic in the caption.</figcaption>
  </figure>
```

## *HTML Book* Chapter 11 - Color

- Colors have RGB values, Hex codes or names
  - CSS Hue
  - Saturation is amount of gray in the color
  - Brightness is the amount of black in the color

- Picking fore and back ground colors depends on environmental conditions, poor equipment and accessibility

- Opacity using rgba property
<!-- From HTMl & CSS book, page 254 -->

```render-css
p.one {
  back-ground-color: rgb(0,0,0);
  opacity: 0.5;}
p.two {
  background-color: rgb(0,0,0);
  background-color: rgba(0,0,0,0.5);}
```

- CSS3 Hue
- Saturation is amount of gray in the color
- Lightness is the amount of black (0%) and white (100%) in the color

## *HTML Book* Chapter 12 - Text

- Serif fonts have th extra feet and tails and neck spaces on older style fonts
  - Georgia, Times,Times New Roman
- sans-serif are straight lined
  - Arial, Verdana, Helvetica
- Monospace is a fixed width for each letter, so m has same width as i
  - Courier, Courier New
- Cursive
  - Comic Sans MS, Monotype Corsiva
- Fantasy
  - Impact, Haettenschweiler
- Font-family limited by licensing and choices
- Font-size use pixels, em or percentages
- Fonts can vary between Mac and PC
- Transforming to upper or lower case using 

```render-css
h1 {
  text-transform: uppercase;
  }
```

## JPEG vs PNG vs GIF Article

[JPEG vs PNG vs GIF](https://blog.imagekit.io/jpeg-vs-png-vs-gif-which-image-format-to-use-and-when-c8913ae3e01d)

- JPEGs for a lot of color
- PNGs for less colors or images with contrasts
- GIFs for animations
