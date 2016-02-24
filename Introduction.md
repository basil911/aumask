<br>

<h1>Advanced Unsharp Mask</h1>

<br>

Unsharp mask is commonly used tool to increase perceived sharpness of image. Or in other words - increase local contrast of image. The Gimp by default contains unsharp mask tool, but that one is very basic. So this plugin exists to improve capabilities of the unsharp mask. See below for more info.<br>
<br>
First, here is the screenshot of version 0.9.0 of the plugin:<br>
<br>
<img src='http://aumask.googlecode.com/files/aumask-0.9.0-window.png' />


<br><br>

<h2>Briew overview of capabilities</h2>

<br>

<h3>Two types of blurring</h3>

<ul><li>Normal (simple blur, this is standard for unsharp mask)<br>
</li><li>Selective (this is my addition, the purpose is to prevent occurence of halo effect between areas with too diferent brightness)</li></ul>

<h3>Four types of output</h3>

<ul><li>Sharpened image (this is expected output of this plugin)<br>
</li><li>Mask (might be important to see when tweaking settings)<br>
</li><li>Splitted mode (to compare the effect)<br>
</li><li>Mask-to-img difference (for "creative" purposes)</li></ul>

<h3>Brightness via mask manipulation</h3>

This tool is intended to manipulate overall brightness and/or contrast of image. Note that this tool works via unsharp mask not an actual value of individual pixels. One of effects is that this way local contrast is preserved.<br>
<br>
<br>
<h3>Alternative colospaces</h3>

Primarily the plugin calculates brightness with own formula, but you can switch to HSV and HSL mode to use value/lightness as a "brightness".<br>
<br>
<h3>R/G/B channel as brightness</h3>

This is a testing feature, it can use one of color channels as a brightness.<br>
<br>
<br><br>

<h2>Introductory step-by-step guide</h2>

<br>

<h3>General notes</h3>

I presume you have plugin installed, because it is better to try it then only read about it. So open any image and start the plugin (Filters - Enhance - Aumask Sharpening). First note - preview is auto-expandable so  you might want to enlarge plugin to have the preview enlarged. There is the <i>Output</i> combo box under the preview, please try out some of options provided there and check results in preview.<br>
<br>
<br>
<h3>1. Simple sharpening</h3>

This is very elementary function of the plugin. It is based on sharpness equalizer. Sliders changes current distance between original and mask and each one controls own distance. Keep mouse over any slider to see actual ammount. Here with this functionality, I'm not sure if <i>sharpness equalizer</i> is that usefull or better then a 'single amount' sharpening. So play with sliders and play with "radius" in the right side. You should have selected "standard blur" mode. Change the view (<i>Output</i> mode) in previews to see an effect. My advice is to keep all sliders in the similar level. And here is an example:<br>
<br>
<a href='http://aumask.googlecode.com/files/forest-example.JPG'>http://aumask.googlecode.com/files/forest-example.JPG</a>

<h3>2. Brightness modification</h3>

One of controls on the right side is <i>Brightness adjustment</i>. This modifies brightness via mask. So the effect is that it preserves local contrast. Usually with this option you will want to compress brightness range of image. So play with those two spinboxes and <i>blur radius</i> as well to see the effect.<br>
<br>
Obligatory example:<br>
<br>
<a href='http://aumask.googlecode.com/files/castle-example.JPG'>http://aumask.googlecode.com/files/castle-example.JPG</a>

<h3>3. Selective mask - Hallo efect elimination</h3>

I believe that you noticed "hallo" efect in areas where two areas with very different brightness met. To avoid this I'm introducting here <i>selective mask</i> ( see combo box in <i>Mask Options</i>). For now you can try <i>Selective mask without postblur</i>. First set <i>Output</i> to <i>Mask</i> and play with various settings - <i>radius</i> and <i>treshold</i>. Afterwards change the <i>output</i> to <i>Image</i> and try to find out if this seems usefull for you.<br>
<br>
<br>
Here is example (sorry no image of mask) and comparison of sharpening with normal and selective mask. The image is split to four strips - original, sharpened with normal mask (note halo above the trees), sharpened with selective mask and last one is sharpened with selective mask after saturation:<br>
<img src='http://aumask.googlecode.com/files/Normal_vs_selective-coast.jpg' />

Below is another example. (I know the photo itself is of poor quality) This example show comparison of masks and resulting images. (Normal and selective)<br>
<br>
<a href='http://aumask.googlecode.com/files/normal_vs_selective.JPG'>http://aumask.googlecode.com/files/normal_vs_selective.JPG</a>

<h3>4. Selective mask - Contrast reduction</h3>

Another purpose of selective contrast mask is reduction of contrast without hallo effect. Note that sharpening here is optional.<br>
<br>
<a href='http://aumask.googlecode.com/files/selective_efficiency.JPG'>http://aumask.googlecode.com/files/selective_efficiency.JPG</a>

<h3>5. Selective mask with postblur</h3>

Sometimes I noticed artifacts on "borders", so I added a "postblur" blurring to the script to soften transitions between areas. I don't have the example now, but keep in mind that such feature is there.<br>
<br>
<h3>6. Mask-to-img difference</h3>

Another possibility (it is up to you what you could do with it) is <i>Mask-to-img difference</i>. Here the output is depending on radius, type of mask, but in addition you can use controls under <i>Mask-to-Img parameters</i>.<br>
<br>
Examples:<br>
<br>
<img src='http://aumask.googlecode.com/files/imask_to_img_diff.jpg' />

last one was done using Selective blur mask, thought differences to normal mask might be not that visible<br>
<br>
<h3>7. HDR</h3>

Another option how to use functionality is something like this.<br>
<br>
<img src='http://aumask.googlecode.com/files/poor_mans_HDR.jpg' />

<br>

<h3>Installation</h3>

If you are linux user, just follow instructions in README (should be trivial), for windows binaries look on <a href='http://www.gimpchat.com/viewtopic.php?f=7&t=6653&p=97528#p97528'>this thread on gimpchat.com</a>. (compilation is not my work)<br>
<br>
<h3>Final note</h3>

Any ideas and feedback is welcomed (to email prefferably: tiborb95 at gmail dot com).<br>
<br>
<br>
<hr />



<i>This plugin is distributed for free and under GPL license. I dont expect earning big money from this, but if the tool is useful / fun to use for you, you can consider paying a voluntary price for the time I spent developing and maintaining it.</i>

<a href='https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=GBERSY833N4AA'><img src='https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif' border='0'></img></a>

<br>

<i>You can also visit homepages (with introduction and examples) of other gimp plugins I made:</i>

<ul><li><a href='http://code.google.com/p/cartooner-color-reducer/wiki/cartoonerIntroduction'>Cartooner - Color Reducer</a>
</li><li><a href='http://code.google.com/p/satequalizer/wiki/Introduction'>Saturation Equalizer</a>