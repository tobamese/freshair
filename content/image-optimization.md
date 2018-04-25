---
title: "Image Optimization"
date: 2018-04-10T16:02:04-04:00
type: "default"
layout: "single"
---

Whenever possible, image assets should be vector to allow us to deliver a single asset that can be scaled across all resolutions. Here we have only included global image file types. There are several newer image file types (like JPEG-X and WebP) which are gaining browser support that we may consider in the future.




### Make it SVG



*   If it's a visual asset that consists of simple, geometric shapes.
*   If it was created in a vector program to begin with.

SVG is an XML based format, so it may end up with some metadata about how it was created that isn't necessary. ImageOptim plugin for Sketch includes SVGO, an SVG optimization tool that will rip it out. SVG is resolution-independent; a single asset can be used across all resolutions.




### Make it PNG



*   If the image includes transparency.
*   If image contains text, since JPEG doesn't handle geometric edges very well.


### Make it GIf



*   If the image includes animations.





### Make it JPEG



*   If the image is a complex visual with lots of detail and no transparency.



And this is where we have a lot more to consider.

One of the benefits of JPEG for large image files is that it is a lossy format. Optimization can take advantage of the way the human eye works to render less pixel data without a perceived loss of quality.  Rather than 'lossless' compression for JPEG, what we want is a compression strategy that yields the lowest impact to PET (psychovisual error threshold) for images while shrinking the payload of image assets.  \


PET is a measure of quality loss perceptible to the human eye.
<img class="block space-top0 space-bottom0" style="width:100%" src="../img/baseline-progressive.png">

One option from a user experience perspective, especially if slow connections are a concern (for example, when users are traveling) are progressive JPEG files instead of baseline JPEGs. Progressive JPEGs render in the browser by flashing a lower quality image upon loading, and gradually increasing the quality as it finishes downloading the full image file. Baseline JPEGs load gradually, at full quality, making the download speed much more noticeable on slower connections.



For our asset delivery

When possible, a designer's eye is the best control for high quality assets.





*   Use Progressive JPEGs so that users get a pixelated version of the image rather than a slow loading image in most browsers
*   Save for Web to strip JPEG metadata
*   Resize images based on breakpoints. Keep pixel density in mind for high-resolution mobile screens.
*   Use ImageOptim & JpegMini to create the smallest JPEG with minimal quality loss.
*   Assets will be included for 3 resolutions: Desktop, @2x, @3x
*   Files should be less than 200k at Desktop resolution, and less than 1MB @3X Hi-Density Resolution



Moving into the responsive system, AKQA will take these steps to ensure images provided are lightweight and impact page speed as little as possible.


### Image Optimization Services



Many Image CDNs include asset compression as a part of their build and delivery. So aside from allowing for the performance advantages of a CDN, they can simplify intelligent, high-quality, device detective responsive image optimization.




**Cloudinary**

Smart image-based compression, responsive images

Uses Akumai as a CDN.

[https://cloudinary.com/](https://cloudinary.com/)

**ImageEngine**

[https://web.wurfl.io/#wurfl-js](https://web.wurfl.io/#wurfl-js)




### Tools





*   Open-source tool using Cloudinary's algorithm for creating optimized, responsive images. [http://www.responsivebreakpoints.com/](http://www.responsivebreakpoints.com/)





*   ImageOptim, image optimizing utility that removes metadata, is powered by a few open-source optimizers and selects the smallest one. Lots of preferences and available as a Sketch plugin. [https://imageoptim.com/mac](https://imageoptim.com/mac)
*   JPEGmini is a paid tool ($29/license) for Mac that can decrease file size even further beyond ImageOptim without quality loss.
<img class="block" style="width:100%" src="../img/figure-output-quality.jpg">





** **
### Citations





*   N. A. Abu, F. Ernawan and N. Suryana, "A generic psychovisual error threshold for the quantization table generation on JPEG image compression," _2013 IEEE 9th International Colloquium on Signal Processing and its Applications_, Kuala Lumpur, 2013, pp. 39-43.
*   [http://www.bookofspeed.com/chapter5.html](http://www.bookofspeed.com/chapter5.html)
*   [https://code.facebook.com/posts/991252547593574/the-technology-behind-preview-photos/](https://code.facebook.com/posts/991252547593574/the-technology-behind-preview-photos/)
*   [https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization)
*   [https://help.figma.com/export/export-options](https://help.figma.com/export/export-options)
*   <span style="text-decoration:underline;">https://jamiemason.github.io/ImageOptim-CLI/comparison/jpeg/jpegmini-and-imageoptim/asc/</span>

<!-- GD2md-html version 1.0β11 -->
