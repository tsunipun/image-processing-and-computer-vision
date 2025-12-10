# Image representation: pixels, channels, and color spaces

## The Digital Image: Pixels and Color Channels  

A **pixel** (short for **picture element**) is the single, smallest physical point in a digital image or display device. It is the fundamental building block that carries the data for a single spot of color.

  

Imagine a mosaic or a grid of tiny colored tiles. Each individual tile is a pixel, and when millions of these tiles are arranged together, they form the complete image you see.

  

### **Pixel Characteristics**

  

-  **Fixed Unit:** Pixels are fixed units of information within a digital file.

-  **Resolution:** The total number of pixels in an image (e.g., $1920  \times  1080$ pixels) determines its **resolution**. Higher resolution means more pixels, which allows for finer detail and clarity.

-  **Pixelation:** If you zoom in on a digital image, you do not "get more pixels." Instead, the existing fixed pixels are simply displayed as larger squares, leading to a blocky, degraded appearance known as **pixelation**.

  

----------

  

### **What a Pixel Contains: Color Information**

  

The primary information contained within a pixel is its **color value**. This color value is defined by one or more **channels** of data.

  

#### **1. Channels and Bit Depth**

  

A **channel** is a single data component that defines a specific characteristic of the pixel's color.

  

-  **Bit Depth:** The **bit depth** of the image determines how many distinct shades or values each channel can represent. For a standard 8-bit image:

- Each channel uses 8 binary bits.

- $2^8 = 256$ possible intensity levels (ranging from 0 to 255).

  

#### **2. Color Spaces**

  

The set of channels and the rules for combining them constitute a **color space** (or color model). This determines how the numerical values are translated into a visible color.

  

|**Color Space**|**Channels**|**Description**
|--|--|--
**RGB**|**R**ed, **G**reen, **B**lue|The most common model for screens and digital cameras. A pixel needs **three** pieces of information to define its color by mixing light.
**Grayscale**|**Luma** (or Intensity)|A monochromatic image. A pixel needs only **one** channel to define its brightness level (from black to white).
**Alpha Channel**|**Alpha** (Opacity)|Often added as a **fourth channel** to RGB to control the pixel's transparency or opacity.

### **The Standard: RGB Pixel Data**

In the widely used **RGB color space**, a pixel is defined by **three channels**, each specifying the intensity of one of the primary colors of light:

  

$$\text{Pixel Color} = (\text{Red intensity}, \text{Green intensity}, \text{Blue intensity})$$

  

- For an 8-bit RGB image, a single pixel requires $8  \text{ bits} \times  3  \text{ channels} = 24  \text{ bits}$ of data to store its color.

- The total number of colors that can be represented is $256  \times  256  \times  256  \approx  16.7$ million colors (often called "True Color").

  

By adjusting the three values, the pixel can display any of these millions of colors.

## The RGB Color Space: The Language of Digital Color

The RGB color space is the fundamental system for representing and displaying colors in digital devices. It uses a combination of three primary components of light: Red (R ), Green (G), and Blue (B).

It is the most widely used color model in digital imaging, computer graphics, monitors, TVs, and phone screens.

### Additive Color Mixing

RGB is based on the principle of additive color mixing, meaning:

-   Adding more light makes the resulting color brighter.
    
-   Every color you see on a screen is created by mixing different intensities of these three colored lights.
    

When the three primary colors of light are combined:

| Combination | Result
|--|--
Red + Green |Yellow
Red + Blue|Magenta
Green + Blue|Cyan
Red + Green + Blue (all at max)|White
Red + Green + Blue (all at zero)|Black

This reliance on emitting or adding light makes the RGB model perfect for digital displays.

  

### How Pixels Store RGB Information

In an RGB system, each pixel stores three numerical values—one for each color channel: Red, Green, and Blue. Together, these values define the final color displayed on the screen.

The values typically range depending on the bit depth:

-   8-bit images (most common): Each channel is represented by an integer from 0 to 255.
    

-   0 means the color is absent.
    
-   255 means the color is at its maximum intensity.
    

-   Floating-point images: Values may range from 0.0 to 1.0.
    

#### Key Color Examples (8-bit):

|Color|RGB Value
|--|--
Pure Red|(255, 0, 0)
Pure Green|(0, 255, 0)
Pure Blue|(0, 0, 255)
White (Brightest)|(255, 255, 255)
Black (Darkest)|(0, 0, 0)
Example Mixed Color|(120, 200, 150)

  
  
  

## The HSV Color Space: The Human Way to See Color

The HSV (Hue, Saturation, Value) color space (also known as HSB for Hue, Saturation, Brightness) is an alternative system to RGB that describes colors in a way that is often more intuitive to human perception and artistic manipulation.

It is derived from the RGB model but separates the color information from the intensity information.

### What HSV Means

HSV uses three distinct, perceptual components to define a color:

|Component|Description|Analogy
|--|--|--
Hue (H)|The pure color (or tint) itself.|The color name (e.g., Red, Green, Blue).
Saturation (S)|The purity or intensity of the color.|How vibrant or dull the color appears.
Value (V)|The brightness of the color.|How much light the color appears to emit.




  

### How HSV Works (The Hexcone Model)

The HSV model is typically represented geometrically as a hexagonal cone or cylinder.4 This structure helps visualize how the three components interact:

1.  **Hue (H)**: Represented by the angle around the central vertical axis.
    

	- It ranges from $0^{\circ}$ to $360^{\circ}$
    
	- $0^{\circ}$ (and $360^{\circ}$) is Red.10
    
	- $120^{\circ}$ is Green.
    
	- $240^{\circ}$ is Blue.
    
	- The value simply selects the base color type.
    

2.  **Saturation (S)**: Represented by the distance from the central axis (radius of the cone).
    

	-   It ranges from 0% to 100% (or 0.0 to 1.0).
    
	-   0% Saturation is a shade of gray (the central axis).
    
	- 100% Saturation is the most vivid, pure color (the outer edge).
    

3.  **Value (V)*: Represented by the height along the central axis.
    

	- It ranges from 0% to 100% (or 0.0 to 1.0).
    
	- 0% Value is always Black (the apex/bottom of the cone), regardless of H or S.
    
	- 100% Value means the color is at its maximum brightness (the top base of the cone).
    

#### Key Color Examples (Ranges are typical for software implementations):

Color | HSV Value (Angle, %, %) | Description
| -- | -- | --
Pure Red|($0^{\circ}$, 100%, 100%)|Full color, maximum brightness.
Mid-tone Red|($0^{\circ}$, 50%, 100%)|Faded red (mixed with white/gray).
Dark Red (Maroon)|($0^{\circ}$, 100%, 50%)|Full color, half brightness (mixed with black).
White|(Any, 0%, 100%)|Zero saturation, maximum brightness.
Black|(Any, Any, 0%)|Zero brightness.

  

### Why HSV is Used

Unlike RGB, where changing one value (like Red) often alters the overall brightness and saturation, HSV allows for independent control over these attributes.

-   Intuitive Manipulation: Designers and artists find it easier to adjust a color by saying "I want this red to be duller (lower Saturation)" or "I want this yellow to be darker (lower Value)" than by guessing RGB triplets.
    
-   Image Processing: It is widely used in computer vision and image editing because separating the intensity (Value) from the color information (Hue and Saturation) makes tasks like color-based object detection and lighting corrections much simpler.
    

  

## The Lab Color Space (CIELAB)

The CIELAB color space, commonly referred to as L*a*b* (pronounced "L star, a star, b star"), is a revolutionary color system defined by the International Commission on Illumination (CIE) in 1976. Unlike RGB or CMYK, it is a device-independent space designed to encompass all colors visible to the human eye and to be perceptually uniform.

This means that a given numerical change in L*a*b* space is intended to correspond to a similar change in color as perceived by a human observer.

----------

###  What L*a*b* Means

L*a*b* is based on the opponent-color theory of human vision, where the brain interprets color information as differences between opposing pairs.4 It uses three coordinates:5

Component|Description|Range (Typical)
|--|--|--
L*|Lightness: The achromatic (non-color) axis.|0 (Black) to 100 (White)
a*|Red-Green Axis: Position between opponent colors.|Negative ($\rightarrow$ Green) to Positive ($\rightarrow$ Red)
b*|Blue-Yellow Axis: Position between opponent colors.|Negative ($\rightarrow$ Blue) to Positive ($\rightarrow$ Yellow)

----------

###  How L*a*b* Works (The Opponent Model)

L*a*b* colors are represented as points in a three-dimensional coordinate system.6

1.  L* (Lightness): This is the vertical axis, completely separate from the color information.7 Adjusting L* changes only the brightness/darkness without affecting the hue or saturation.8
    
2.  a* Axis: This runs horizontally, where negative values trend toward Green and positive values trend toward Red.9
    
3.  b* Axis: This runs perpendicular to the a* axis, where negative values trend toward Blue and positive values trend toward Yellow.
    

#### Key Color Examples:

Color|L* Value|a* Value|b* Value
|--|--|--|--
Pure White|100|0|0
Neutral Gray|50|0|0
Pure Black|0|0|0
Saturated Red|~50|Positive High|~0
Saturated Yellow|~90|~0|Positive High

### Key Features and Use Cases

-   Device Independence: L*a*b* is not tied to the color gamut of a monitor (RGB) or a printer (CMYK). This makes it the ideal universal color reference for consistent color reproduction across different media and devices (e.g., matching a fabric color to a brand's printed logo).
    
-   Perceptual Uniformity: Because numerical differences (calculated as $\Delta E$, or "Delta E") are closely aligned with human perception, L*a*b* is used extensively in Quality Control (QC) across industries (textiles, food, plastics) to precisely measure and set tolerances for color accuracy.
    
-   Color Conversion Bridge: In professional graphics software (like Adobe Photoshop), L*a*b* often acts as an intermediate color space when converting between device-dependent color spaces (e.g., RGB to CMYK) to preserve color accuracy and minimize shifts.
    
-   Independent Channel Adjustment: Like HSV, L*a*b* separates lightness (L*) from chromaticity (a* and b*), allowing retouchers to adjust the contrast/tonality of an image without introducing color shifts.
    

##  The YCbCr Color Space: The Digital Video Standard

The YCbCr color space (often written as $\text{Y}'\text{CbCr}$ to denote gamma-corrected components) is a family of color spaces primarily used in digital video, image compression (like JPEG), and television systems. It is mathematically transformed from the RGB space but separates the image information into brightness and color components.

Its design is rooted in the way the human visual system processes information, allowing for highly efficient data compression and transmission.

----------

### What YCbCr Means

YCbCr separates the image data into one luma (brightness) component and two chrominance (color) components:

Component|Full Name|Description|Role
|--|--|--|--
Y ($\text{Y}'$)|Luma (Luminance)|Represents the brightness or grayscale information of the image.|Carries the fine detail to which the human eye is most sensitive.
Cb|Chroma Blue (Blue-difference)|Encodes the difference between the Blue component and the Luma ($\text{B}-\text{Y}'$).|Contains the blue/yellow color information.
Cr|Chroma Red (Red-difference)|Encodes the difference between the Red component and the Luma ($\text{R}-\text{Y}'$).|Contains the red/cyan color information.

Note: The $\text{Y}'$ component is a weighted sum of the $\text{R}'\text{G}'\text{B}'$ values, giving more emphasis to Green, as the human eye is most sensitive to green light.

----------

### How YCbCr Works (Chroma Subsampling)

The key advantage of YCbCr is that separating Luma (Y) from Chroma (Cb and Cr) allows for Chroma Subsampling. This is a form of lossy compression that takes advantage of a physiological fact: the human eye is far more sensitive to brightness (Luma) detail than to color (Chroma) detail.

In subsampling, the color data (Cb and Cr) is stored at a lower resolution than the brightness data (Y), which significantly reduces file size and bandwidth requirements with minimal perceived loss of quality.

#### Common Subsampling Formats (Ratios of Y:Cb:Cr)

Format|Description|Pixels per 4x2 Block|Bandwidth Reduction
|--|--|--|--
4:4:4|Full Resolution. All Y, Cb, and Cr are sampled equally.|8 Y, 8 Cb, 8 Cr|None
4:2:2|Horizontal Subsampling. Chroma is sampled at half the horizontal resolution of Luma.|8 Y, 4 Cb, 4 Cr|33%
4:2:0|Horizontal and Vertical Subsampling. Chroma is sampled at half resolution in both directions.|8 Y, 2 Cb, 2 Cr|50%

The most common format for consumer video, streaming, and JPEG compression is 4:2:0, due to its high efficiency.

----------

### Key Features and Use Cases

-   Compression Efficiency: The primary reason for YCbCr's dominance in video encoding (MPEG, H.264, H.265) and image formats (JPEG).
    
-   Legacy Compatibility: Its analog predecessor, YUV/YPbPr, was designed to allow black-and-white television sets to display a colored signal as monochrome (by only processing the Y component), demonstrating the value of separating brightness.
    
-   Digital Video Transmission: It is the standard format for digital video interfaces like HDMI and SDI for transmitting high-definition video signals efficiently.
    

- Processing: It allows for the Luma channel to be processed (e.g., sharpening, noise reduction) independently of the color information, which can lead to better visual results.