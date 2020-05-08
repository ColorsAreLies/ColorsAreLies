# ColorsAreLies Outline

* Main Page = Table of Contents
    * unless we use that fancy Jekyll theme
* Introduction
* Overview
    * Goals of ColorsAreLies
    * Disclaimers
        * If anything is wrong, PRs welcome
        * Living document; not necessarily comprehensive
    * Reading Order
* Color Vision
* Color Spaces
    * RGB
    * YUV
    * CMYK
    * XYZ
        * "rosetta stone" of RGB color gamuts
* Color Primaries
    * Wave lengths?
    * CIE1931 Chromaticity Diagram
    * Gamuts
* Transfer Functions
    * What/Why?
    * Types
        * Gamma
        * SRGB
        * PQ
        * HLG
    * Signaling in color profiles (links to Color Profiles)
* Bit Depth
    * Explanation
    * Banding
    * Odd independence to other factors
* Subsampling
    * What/Why
    * Types
        * 444
        * 422
        * 420
* Luminance Range
    * How bright is float(1.0, 1.0, 1.0)
    * Each chromaticity has its own maxY
        * Link to xyy 3d graph?
    * Overranging
    * Tonemapping
* Signal Range
    * Limited / Full
    * Y vs UV
* Conversion Pipeline
    * Pipeline
        * src unorm curved RGB -> src float curved RGB (src depth)
        * src float curved RGB -> src float linear RGB (src curve)
        * src float linear RGB -> XYZ (src primaries)
        * XYZ -> xyY
        * scale Y based on luminance scales
            * tonemap if necessary
        * xyY -> XYZ
        * XYZ -> dst float linear RGB (dst primaries)
        * dst float linear RGB -> dst float curved RGB (dst curve)
        * dst float curved RGB -> dst unorm curved RGB (dst depth)
    * Optimizations
        * if not scaling Y, concatenate matrices in the middle
        * lookup table for src unorm curved RGB to src linear float RGB
        * lookup table for dst float linear RGB to dst curved unorm RGB
        * fragment shader
* Color Profiles
    * Link back to each section
    * Types
        * Images - ICC Profiles
            * color.org
            * Issues with PQ and HLG
        * Video/HEIF/AVIF - CICP (nclx)
            * https://www.itu.int/rec/T-REC-H.273-201612-I/en
* Technologies
    * HDR10
    * DVLL
    * IMF Essences (P3 PQ) ?
