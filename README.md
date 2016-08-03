# SelectiveSearchCodeIJCV
SelectiveSearchCodeIJCV 原代码来自于[Homepage of Jasper Uijlings](http://disi.unitn.it/~uijlings/MyHomepage/index.php#page=projects1)

## SELECTIVE SEARCH FOR OBJECT LOCALISATION
![](http://disi.unitn.it/~uijlings/MyHomepage/Projects/SelectiveSearchObjectExamples.jpg)

Multiple strategies are needed to find all objects in the above images. In (a) the spoon is in the salad-bowl which is on the table. Hence an image is intrinsically hierarchical and we need all scales to find these objects. In (b) the cats can be separated by colour and not by texture, while in (c) the reverse holds for the cameleon. In (d) the wheels are part of the car because they are enclosed by the body while they wildly differ in both colour and texture.

Segmentation traditionally tries to find a single partitioning of the image into its unique objects before any recognition. As this is extremely hard if not impossible (see figure below), researchers resorted to localise objects through recognition by performing an exhaustive search within the image (i.e. sliding window method). But this ignores all useful information in low-level cues. Therefore we propose to combine the best of both worlds into a data-driven Selective Search: We exploit the structure of the image as in segmentation. We aim to generate all possible object locations as in exhaustive search.

We propose to diversify the sampling techniques to account for as many image conditions as possible:
* We use a hierarchical grouping to deal with all possible object scales
* We use a diverse set of grouping strategies and vary:
<1> The colour space of the image to deal with different invariance properties
<2> Region-based similarity functions to deal with the diverse nature of objects. In particular we use as similarities colour, texture, size, and/or a measure of insideness.

The final algorithm is fast and accurate: within 4 seconds it can generate 2,134 boxes with an Average Best Pascal Overlap score of 0.804. The small set of good quality boxes allows us to do object localisation using Bag-of-Words. With this system we won the ImageNet Large Scale Detection challenge 2011 and the Pascal VOC Detection Challenge 2012.
![](http://disi.unitn.it/~uijlings/MyHomepage/Projects/SelectiveSearchGraph.jpg)
![](http://disi.unitn.it/~uijlings/MyHomepage/Projects/SelectiveSearchObjectsFound.jpg)

