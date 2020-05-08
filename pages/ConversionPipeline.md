# Conversion Pipeline

A typical conversion from one color space to another has these steps (staring with values in the
source color space):

1. Convert integer to normalized float
1. Linearize (apply EOTF)
1. Source to XYZ (matrix multiply)
1. Convert to xyY
1. Scale luminance by source/destination luminance
1. Modify colors (optional)
1. Convert to XYZ
1. Tone map or clip (for smaller destination luminance)
1. XYZ to destination (matrix multiply)
1. Curve (apply OETF)
1. Covert float to integer

You may also need to clamp values to 0.0-1.0 in some places.

The final values after these steps will be in the destination color space.

If you remove the optional modification step and no luminance scale is needed, please note that the
matrix multiplies can be combined into a single operation:

1. Convert integer to normalized float
1. Linearize (apply EOTF)
1. Source to destination (matrix multiply)
1. Curve (apply OETF)
1. Covert float to integer

If your source and destination spaces are the same, but you want to modify the colors, note that the
simplified steps look like this:

1. Linearize (apply EOTF)
1. Modify colors
1. Curve (apply OETF)

This is important, and there's lots of software that doesn't do this correctly. When changing colors
you should really be in linear space, otherwise you can get bad looking results (blending green and
red in gamma space is a classic example of this).
