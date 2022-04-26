# gfm-playground

Testing how text, images, and other elements are actually rendered into HTML from Markdown is important when crafting a non-trivial `README.md`. For this purpose, I (Bryce Carson) created an SVG image from a GNU logogram using a typographic template in Inkscape. The SVG file, as created, serves as a success-case for the following tests. The test image, `drawing.svg`, is rendered at half the original size using GitHub-permitted in-line CSS styles (`<img src="" style="width:WIDTHpx;height=HEIGHTpx;">`).

<div align="center"><img src="drawing.svg" style="width:500px;height:500px;"></div>

The rectangles were used to split the image into different parts, based on the x-height (the grey rectangle above the auburn and below the magenta).

<div align="center"><img src="drawing-layered.svg"></div>

It is barely discernible, but you can see a very small rendering issue where the paths composing the two horns were divided using the magenta rectangle. The rendering issue is due to the browser, and may not appear in other browsers (I am running Google Chrome `Version 100.0.4896.127 (Official Build) (64-bit)` on Fedora 36 Beta).

Although this rendering issue exists it is not part of the SVG image.

# Tests
1. Does the image render as it was drawn?<br><div align="center"><img src="drawing-screenshot.png" style="width:569px;height:439px;"></div>

2. Can the image be reassembled after splitting it along the guide-lines? How large is the padding on different displays? No alignment divs are used in this test.<br>The canvas size is adjusted to each remainder in the image after path division; the canvases, placed atop each other, should add up to 1000 pixels.<br>
<img src="drawing-part-one.png">
<img src="drawing-part-two.png">
<img src="drawing-part-three.png">
<br>
The three rendered images are not placed directly after one another. How does this compare to standard HTML rendering?

3. Can the images be vertically joined in standard HTML?<br>
