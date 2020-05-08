# Conversion Pipeline

A typical conversion from one color space to another has these steps (staring with values in the
source color space):

1. Normalize values (0.0-1.0, if needed)
1. Linearize (apply EOTF)
1. To XYZ (matrix multiply)
1. Scale luminance (by src/dest luminance)
1. Convert to xyY (optional)
1. Modify colors (optional)
1. Convert to XYZ (only for xyY case)
1. Tone map or clip (for smaller dest luminance)
1. From XYZ (matrix multiply)
1. Curve (apply OETF)
1. De-normalize values (to bit depth, if needed)

You man also need to clamp values to 0.0-1.0 in some places.

The final values after these steps will be in the destination color space.

If you remove the optional middle steps, please not that the matrix multiplies and scale can be
combined into a single operation (assuming no tone map is needed):

1. Normalize values (0.0-1.0, if needed)
1. Linearize (apply EOTF)
1. Source to destination (matrix multiply)
1. Curve (apply OETF)
1. De-normalize values (to bit depth, if needed)

If your source and destination spaces are the same, but you want to modify the colors, note that the
simplified steps look like this:

1. Linearize (apply EOTF)
1. Modify colors
1. Curve (apply OETF)

This is important, and there's lots of software that do this. When changing colors you should really
be in linear space, otherwise you can get bad looking results (blending green and red in gamma space
is a classic example of this).
