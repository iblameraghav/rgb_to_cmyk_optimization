# rgb_to_cmyk_optimization
RGB To CMYK Optimization Tool Using Colormath

This topic is about creating a visualisation and optimization tool for CMYK-based printing using
computer vision and image processing in Python.
Here an RGB image is taken as input with spiked up saturation and was converted to CMYK to color
space using numpy operations. Each CMYK component was taken in a grayscale ink separation plate
and served as an independent image. The total ink consumption per pixel was computed as the sum of
all 4 CMYK channels which results in calculation Total ink coverage (TIC). These values reach up to
the total of 400% if we’ll consider the maximum normalized value of CMYK as (1 + 1 + 1 + 1)*100.
Therefore, excessive ink deposition can lead to print quality issues, bleeding of ink and slow drying.
Ink limitations are implemented to keep them under the practical threshold of 250% to 300%.
After ink limitation, these CMYK images are converted back to RGB for visual comparison. To
evaluate the loss that is beared while transformation, CIEDE2000 Delta E operations are performed.
The result afterwards, preserve the excessive CMYK usage while preserving the visible appearance
of the image under the threshold of 250% and 300%.


