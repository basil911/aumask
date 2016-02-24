# Partial algorithm of advanced unsharp mask #

Goal of this wiki is to

  1. explain how RGB values are processed by individual colorspaces
  1. provide room for discussion and description of implementation of other color modes - as required by users


# Current processing as by 0.8 version: #


The plugin offers three colospaces. So it emploies different approaches to get brightness of pixel (that is used for mask) and at the end it used backward algorithme to modify original RGB values of pixel

| step/colorspace | OWN | HSV | HSL |
|:----------------|:----|:----|:----|
| initial conversion | r = (R/255)^(1/2.2) | r=R/255 | r=R/255 |
| calculating value| 0.299\*t + 0.587\*g + 0.114\*b | gimp\_rgb\_to\_hsv | gimp\_rgb\_to\_hsl |
| getting new brightness | common algorithm |
| getting new values (floats 0-1) | RGB differences added to new brightness | gimp\_hsv\_to\_rgb() where v is changed | gimp\_hsl\_to\_rgb() where l is changed |
| getting int (0-255) | r^2.2\*255 | r\*255 | r\*255|


few comments to the table

  * R,G and B are used for integers 0-255
  * r,g and b are used for floats 0-1
  * in lines where I list only formula for r, the same is used for g and b
  * values below 0 and above 1 are clipped before conversion to final RGB.


This page is incomplete and I dont work on it. If you are interesting in more details, let me know -by email if possible