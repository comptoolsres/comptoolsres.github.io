---
title: "Graphics"
tags: [misc]
sidebar: home_sidebar
permalink: Graphics.html
sidebar: home_sidebar
summary: Much research data starts as images and/or is presented in graphical formats. Understanding some concepts will make working with graphics easier and also allow you to understand the guidelines around editing images of research data.
keywords:
---

## Two main types of graphics

There are two main types of graphics files: **<a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.raster_image}}">raster images</a>** and **<a href="#" data-toggle="tooltip" data-original-title="{{site.data.glossary.vector_image}}">vector art</a>**. Raster images are also called bitmap or pixel images--these tend to be photos, sensor images, scanned files, etc. Vector graphics are illustrations or art made with software that uses mathematical or programmatic instructions to define the objects in the image.

{% include image.html file="StickerYou_Blog_Vector-vs-Bitmap_600x400.jpg" alt="Image showing difference between vector and bitmap images from StickerYou.com." %}

As the image above shows, as you enlarge a vector image, it will continue to have smooth curves and lines. Bitmaps, however will start to show the individual pixels as they become large enough to be seen, resulting in jagged edges and blurriness.

{% include note.html content="One rule of thumb in deciding which type of image format to use is: if you are creating the image on the computer, use vector images where possible. If your are using a camera, sensor or other input, the image will likely be a raster image." %}

Type  | Vector Art | Raster Image
------|------------|--------------
      | Infinitely scalable | Set pixel dimensions
      | Sample formats: <br>  PDF, EPS, SVG, AI | Sample formats:<br>  PNG, JPEG, TIFF, BMP
In print| Most figures in a printed paper | Printed photos
For screen, web or presentations | Diagrams, graphs, maps *  | Photos

*I frequently make my web images as vector art, then export as PNG for websites.

## Raster images

Common raster image applications:

* [Adobe Photoshop](https://www.adobe.com/products/photoshop.html)
  * Powerful, but expensive
* [Gimp](https://www.gimp.org/)
  * Free, open source, but can be harder to use and somewhat limited
* [Affinity Photo](https://affinity.serif.com/en-us/photo/)
  * Similar to Photoshop, but much less expensive!

Common raster image formats:

* JPEG-8-bit to 24-bit color. Usually lossy
* TIFF--flexible, has many implementations. Up to 48-bit color. Can be lossless.
* RAW--minimally processed data from the image sensor (a digital negative). Differ from manufacturer to manufacturer.
* PNG--Patent-free replacement for GIF. Often used for web images. up to 48-bit color.

## Resolution

The **resolution** of raster images refers to the number of **dots** (in print) **or pixels** (on screens) **per inch** (in the US) or cm (in the rest of the world). This image below shows four rasters of different resolution. Each is a 1-inch square, but they have different resolutions: 1, 2, 4, and 16 pixels per inch or PPI.

{% include image.html file="1_5d59TmmRUrquCuOMk3nuNw.png" alt="credit: https://blog.prototypr.io/designing-for-multiple-screen-densities-on-android-5fba8afe7ead Image showing different pixel resolutions" %}

Historically, monitors were designed with 72 ppi and magazine quality photos were printed at 300 dpi. While print has remained at about 300 dpi standard, because of so many different sizes and types of screens, and the distance from which they are viewed, screen ppi's vary quite a bit from the standard 72 ppi to almost 500 ppi on high-end phone screens.

A raster image can be downsized to display at a lower resolution, but cannot be shown with more pixels than are in the original image. It is typically best to save images with the highest resolution possible to avoid loss of information.

For publication, most journals request 300 dpi resolution for raster images.

## Resolution and size

It is important to understand that **image resolution and size are related**. If you have an image that is 3,000 pixels by 3,000 pixels in size and you are preparing it for print at 300 dpi, this image would be 10 inches by 10 inches. If that is the size you want, you are fine. But there is no way to make the image 20 inches by 20 inches at 300 dpi.

It is important to understand how big the image will be in print and the resolution, to know how many pixels are needed to achieve those results.

## Additive vs Subtractive Color

Monitors, TVs and projectors create colors additively--add wavelengths of light to create the desired . Print is subtractive, more pigment is added to absorb light of certain wavelengths to reflect only the desired wavelengths.

{% include image.html file="additive_subtractive_colors.png" %}

These differences in how colors are produced and which colors used to produce the desired color sometimes make differences in how images are displayed. This relates to the next section, color space.

## Color space

Your eyes, different screens and different printing technologies can perceive and produce different ranges of colors--this is referred to as the color space or gamut. The image below shows an approximation of the visible color gamut, and some other common color spaces.

{% include image.html file="colorspace.png" %}

When selecting colors for figures, keep color spaces in mind along with how the image will be used. Depending on your screen the image below may or may not show some of the simulated differences among the image colors. If the point of the figure relies on the differences among colors that, in one particular color space cannot be distinguished, that is not a good choice of colors.

{% include image.html file="colorspace_example.HaddockDunn.png" caption="Example of color space differences from Haddock and Dunn, <i>Practical Computing for Biologist</i>, 2010." %}

## Color choices: Color blindness

When selecting colors for images, consider your audience and understand issues of color blindness.

{% include image.html file="Eight_Ishihara_charts_for_testing_colour_blindness,_Europe_Wellcome_L0059163.jpg" caption="Colour blindness is tested using these eight placards. They are known as Ishihara charts. They are named after their inventor, Japanese ophthalmologist Shinobu Ishihara (1897&#150;1963). Each image consists of closely packed coloured dots and a number. The patient must identify the number or image he or she can see. The type of colour blindness a patient has is identified using the range of charts. There are several types of colour blindness. These range in severity. In dichromatism, there is difficulty seeing one of the three primary colours: red, blue or green. In anomalous trichomatsis, there is reduced sensitivity to certain colours. In the rarer monochromatism, there is no colour vision and the world is seen in white, black and grey shades. Ishihara devised his test in 1917. It is still used. This file comes from Wellcome Images, a website operated by Wellcome Trust, a global charitable foundation based in the United Kingdom." %}

## Color choices: Aesthetics and visibility

Also consider aesthetics and visibility!

{% include image.html file="bad-web-design-colors-combination-thumb.jpg" caption="Image from: http://designwebkit.com/web-and-trends/color-combinations-hell-death-sentence-designs/" %}

## Color depth

Similar to data types and the idea of using different number of bits to store an integer, you can use different numbers of bits to store the colors in images. More bits translates to more colors, but also large files sizes.

{% include image.html file="color_depth.png" caption="Example image saved at different color depths. Images from https://en.wikipedia.org/wiki/Color_depth" %}

## Image Compression

* Lossless
  * De-compresses to original values
  * LZW (TIFF)
  * JPEG 2000 (can be lossy)
* Lossy
  * Cannot de-compress to original values, only approximations
  * JPEG is ver common web format
    * High compression ratio --> Lower bandwidth
    * Selective compression: Lossless to more compression

The images below show the loss of detail with higher compression.

{% include image.html file="image_compression.png" %}

## Beyond visible light

Increasingly imaging sensors capture wavelengths of light beyond what humans can see. These hyperspectral images can offer insights into temperature, photosynthetic productivity and more. The images are often transformed into the visible spectrum for analysis.

{% include image.html file="hyperspectral_imaging.png" %}

## Vector Images

The number one thing...**don't use PowerPoint!!** It's great for presentations, but if your goal is to produce publication ready images, PowerPoint is the wrong tool!

Common vector art applications:

* [Adobe Illustrator](https://www.adobe.com/products/illustrator.html?promoid=PGRQQLFS&mv=other)
  * Powerful, but expensive
* [Inkscape](https://inkscape.org/)
  * Free, open source, but can be difficult and limited features
* [Affinity Designer](https://affinity.serif.com/en-us/designer/)
  * Similar to Illustator, but less expensive

Common vector image formats

* PDF--Adobe proprietary, though somewhat open
* SVG--Scalable Vector Graphics; an open standard
* EPS--Encapsulated PostScript; often used for printers
* AI--Adobe Illustrator format

## Bézier curves

Bézier curves are sets of polynomial equations used to model the objects (paths) in vector graphics. Because the paths are defined by scalable equations, resterization is not an issue and they can scale easily. Bézier curves are also used in animation where they describe the physics of motion.

{% include image.html file="Bezier_4_big.svg.png" %} 

{% include image.html file="Bezier_4_big.gif" %}

## Scripting your graphics

There are tools to create and modify both raster and vector graphics. We have already looked a bit at [making plots with matplotlib](https://github.com/comptoolsres/Jupyter_content/blob/main/Data_visualization.ipynb).

* Many graphical Python applications use [PyQT](https://riverbankcomputing.com/software/pyqt/intro)
  * There's also the [PyQtGraph](http://www.pyqtgraph.org/) module
* For more ideas, check out this page on [Graphical Representations of Data](https://wiki.python.org/moin/NumericAndScientific/Plotting)

Here's an example of using PIL to identify *C. elegans* (nematodes) in an microscope image.

{% include image.html file="celegans_pil.png" %}

## Image ethics

Given that just about every image is digital, and most will have *some* post processing done on them, how much is too much??

* Correcting the exposure?
* Removal of dust?
* Cropping to remove part of the field of view?
  * What if the cropped area differs from the story being told?
* Clone a portion of an image and replicate?

The following are images from [Rossner and Yamada (2004)](https://rupress.org/jcb/article/166/1/11/34064/What-s-in-a-picture-The-temptation-of-image).

{% include image.html file="RossnerYamadaFig1.jpeg" caption="Gross manipulation of blots. (A) Example of a band deleted from the original data (lane 3). (B) Example of a band added to the original data (lane 3)." %}

{% include image.html file="RossnerYamadaFig4.jpeg" caption='Manipulation of blots: cleaning up background. The Photoshop "Rubber Stamp" tool has been used in the manipulated image to clean up the background in the original data. Close inspection of the image reveals a repeating pattern in the left lane of the manipulated image, indicating that such a tool has been used.' %}

{% include image.html file="RossnerYamadaFig5.jpeg" caption="Misrepresentation of immunogold data. The gold particles, which were actually present in the original (left), have been enhanced in the manipulated image (right). Note also that the background dot in the original data has been removed in the manipulated image." %}

{% include image.html file="RossnerYamadaFig6.jpeg" caption="Misrepresentation of image data. Cells from various fields have been juxtaposed in a single image, giving the impression that they were present in the same microscope field. A manipulated panel is shown at the top. The same panel, with the contrast adjusted by us to reveal the manipulation, is shown at the bottom." %}

Another great source for this kind of image manipulation is Elisabeth Bik (on Twitter [@MicrobiomDigest](https://twitter.com/MicrobiomDigest), Blog [Science Integrity Digest](https://scienceintegritydigest.com/))

{% include image.html file="elisabeth_bik.png" %}

Also see [@RetractionWatch](https://twitter.com/RetractionWatch)

For suggested guidelines, see:

* *Nature*: [Image Integrity and Standards](https://www.nature.com/nature-research/editorial-policies/image-integrity)
* Elsevier: [Five things every researcher should know about image manipulation](https://www.elsevier.com/connect/authors-update/five-things-every-researcher-should-know-about-image-manipulation)
* Check the journals in your field or where you plan to publish. Keep and share original images.