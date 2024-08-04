---
title: "OSINT and what you need to know about satellites"
authors: 
    - name: "Albin Touma"
      link: https://github.com/AlbinTouma
      image: https://avatars.githubusercontent.com/u/107361490?v=4
draft: true
---

Satellites orbit Earth, capturing images with sensors sensitive to specific electromagnetic wavelengths. These sensors can detect various wavelengths from visible light (red, green, blue) to infrared and UV. Different wavelengths interact uniquely with matter, revealing different colors and features. For instance, vegetation strongly reflects infrared light, making it easily visible in infrared images. The custom script helps us place different bandwidths in different colours and manipulate the brightness of these colours to exaggerate objects. Evalscript 

Bands - Narrow wavelength ranges in satellite channels create images. Different bands highlight different objects. 

Spectral signature - each object has a unique spectral signature based on how it absorbs and reflects light. Identifying this helps in distinguishing objects in satellite images. 

Target Interaction - Visibility depends on absorption, reflection, and scattering of light. Specular reflection (smooth surfaces) and diffuse reflection (rough surfaces) affect how objects appear.

Band calculations - Combining bands using primary colours (RBG) creates composite images. True colour composites mimic human vision while false colour composites use different band combinations to highlight specific features. 

Enhancing satellite images: Adjusting bands enhances visualisations of certain objects such as vegetation or water. 

Custom scripts - We can use the evalscript to manipulate band values and create composites, highlighting features and measuring values like vegetation health  through calculating indices like NDVI. 

## Satellites and the electromagnetic spectrum

Satellites orbit the Earth and capture images with light sensors. Each sensor is sensitive to a specific electromagnetic wavelength on the electromagnetic spectrum. Different wavelengths interact differently with matter and reflect different coloured light. For example, plants reflect red and blue light (this is why they appear as green). Plants also strongly reflect parts of the infrared spectrum so an infrared image clearly shows vegetation.  Colours exist on different wavelengths and a satellite’s light sensors determine the range of colours captured:

- Violet: 0.4 - 0.446 µm
- Blue: 0.446 - 0.500 µm
- Green: 0.500 - 0.578 µm
- Yellow: 0.578 - 0.592 µm
- Orange: 0.592 - 0.620 µm
- Red: 0.620 - 0.7 µm

Optical satellites capture visible light (red, green, blue), infrared, and sometimes UV whereas radar satellites work in the microwave part of the spectrum. By targeting different wavelengths on the electromagnetic spectrum we get different images of the earth called “bands”.

We can enhance images and improve visualisations of certain objects by playing with the colour composite of bands. As you can see from above, the true colour composite (left) was enhanced by adjusting bands to capture wavelengths associated with vegetation and the ocean (right). FOBs may be more visible on a specific range of wavelengths which is why users should be able to configure wavelengths. 

## Spectral Signature

The reason why FOBs may be more visible on a specific range of wavelengths is because different objects absorb or reflect wavelengths. The more an object is reflective the easier it is is to see. How much light an object absorbs or reflects is known as an object’s spectral signature.  If we know an object’s spectral signature, we can accentuate this object in the satellite image by targeting the right combination of wavelengths. This is why FOBBER should try to identify the spectral signature of FOBs in different conditions. 

As the figure above shows, water, soil, and green vegetation have their own signatures as do forward operating bases.  For example, if you have a satellite band with a wavelength of 2.1 um, both soil and green vegetation are reflective whereas water is not. At this satellite band, soil is bright since its reflectance is high (50%), green vegetation is darker grey (reflectance is 20%), and water is black (reflectance is 0%). The success of finding FOBs largely comes down to finding the right signature. 

## Target interactions & Spectral response

The visibility of an object is not only determined by their wavelength.  How light is absorbed or scattered also determined how easy it is to find. Absorption is when light, which is energy,  is absorbed into the target and passes through. Reflection occurs when energy bounces off the target and is redirected. In remote sensing, we focus mainly on energy reflected from targets and there are two types: specular reflection and diffuse reflection.

When a surface is smooth we get specular or mirror-like reflection where almost all energy is directed away from the surface in a single direction. Diffuse reflection occurs when the surface is rough and energy is reflected in all directions. 

If wavelengths are smaller than the surface variations (or particle sizes that make up the surface) diffuse reflection dominates. Fine grained sand would appear smooth to long wavelength microwaves but rough to visible wavelengths. 

Leaves act as an excellent diffuse reflector of near-infrared wavelengths and if we could see in IR, trees would appear as extremely bright (which is how we measure health of forests).

Water appears differently depending on sediment and algae presence which have different wavelengths. In addition the surface of water and any materials on the water complicate water-related interpretation because of potential problems with specular reflection and influences on colour and brightness.

How easy it is to find a target is then determined by the make-up of its wavelengths of radiation, absorption, surface reflection. By measuring the energy reflected by targets over different wavelengths we can build up a spectral response for that object and by comparing response patterns of different features we may distinguish between them where we mightn’t if we looked at only one wavelength. Look again at the raw satellite image and the bands adjusted for vegetation. 

## Band calculations to create a satellite image

Information from a narrow wavelength range is stored in a channel, sometimes called a band. Each satellite band is an image represented as a grid of values in computers (also called a raster). Every grid cell is a pixel. 

In constructing our image, we combine and display bands of information digitally using primary colours (blue, green, red). The data from each band is represented as one of the primary colours depending on relative brightness (ie its digital value) of each pixel in each channel. Primary clours combine in different proportions to represent different colours. 

We can use map algebra to perform calculations between different satellite bands by calculating between corresponding pixels. We can add, subtract, and multiply and divide bands. 


The table below lists Sentinel-2 satellite’s different wavelengths and spatial resolutions in meters. 

Band/RBG value

Wavelength

Spatial Resolution (meters)

Band 1 - B01

Coastal Aerosol

0.421 – 0.457

60

Band 2 - B02

Blue

 0.439 – 0.535 

10

Band 3  - B03

Green 

0.537 – 0.582

10

Band 4 - B04

Red

0.646-0.685

10

Band 5 - B05

Vegetation red edge

0.694 - 0.714

20

Band 6 - B06

Vegetation red edge

0.731-0.749

20

Band 7  - B07

Vegetation red edge

0.768-0.796

20

Band 8 - B08

Near infrared (NIR)

0.767-0.908

10

Band 8a -  ?

NIR

0.848-0.881

20

Band 9 - B09

Narrow NIR

0.931-0.958

60

Band 10 - ?

Cirrus

1.338-1.414

60

Band 11  - ?

Short wave infrared (SWIR)

1.539-1.681

20

Band 12 - ?

Short wave infrared (SWIR)

2.072-2.312

20

 

## True vs false colour composites
 

Humans have 3 colour receptors: red, blue, green. Computers use RBG colour model to represent colours where R is for red, G for green, B for blue. We call those colour channels. Every colour on a computer contains certain amounts of red, blue, green light. Values range from 0-255 for every channel, adding up to 16.7 million different colours. Pure red will have 255 in the red channel, 0 in green and blue. If we had 225 for red and blue we get purple. 

The higher the value in a channel the more of the colour is mixed in and if all three have equal values, we get a colour in black and white range; white if all three are 255 and black if all three are 0. 

 To get a colour image we create it by combining 3 bands and putting them into the red, green, and blue channels. The band we choose to input into red channel will appear as red on the image etc. This resulting image is called composite. 

 
If we input a red wavelength (a red band) into red channel and green and blue into respective channels we get a colour image that humans see naturally. In Sentinel-2, bands corresponding to red, green, blue light are B04, B03, and B02 respectively. 

We can put any band into any of the three RBG channels. Images where red, green, and blue bands are fed to respective bands are are called true colour composites. A composite that is not a true colour composite is called a false colour composite and this is an image where we place a red band in one of the other colour channels.

If we input the same band into all 3 colour channels we lose RGB properties and get a grayscale image of the band. 

To highlight vegetation, we could place band 8  (near infrared) into the red channel, band 4 (red), into the green, and band 3 (green) into the blue channel.

Red - Band 8 Infrared, Band 4 (red) in green, band 3 green in blue
If we put band 8 inside blue channel instead, we would get the same image but with blue colour. This is because some bands are brighter than others and have different bandwidths (band wavelength range from min to max), different spatial resolutions, and that the amount of electromagnetic energy varies with wavelength. 

We can use a custom script to multiply bands and make the less dominant band stronger. 

## Presenting Results with Custom Script

By default, True color option is selected. To make a simple true color composite return an array that defines the colours for visualisation:

``return [B04, B03, B02]``

Using the same band 3 times is the same as returning only one band and this yields a grayscale image. 

We can manipulate bands by numerical values. Multiplying each band by 2.5 is useful for Sentinel-2 true colour composites as it improves appearance of images. 

``return [B04*2.5, B03*2.5, B02*2.5]``
 
Multiplying increases the brightness of a colour. Below are two true colour composites. On the left is without multiplying values and on the right is multiplication by 2.5

Vegetation has high reflection in infrared (band 8). We can make a false colour composite where vegetation appears as red or green by inputting band 8 into the red channel and high values for non-vegetated areas in green and blue: 

``return [B08*2.5, B04*2.5, B03*2.5] //red vegetation 
 ``

We can put any value we want in our script. 

```
let value = B11 + B02;
return[value]
```
This means that we can perform any calculation that we like such as NDVI index which shows vegetation health and assign colours to differnt NDVI classes with if statements:
```
var NDVI = index (B08, B04); // calculate the index
if (NDVI < 0.2) {
 return [0.3, 0.2, 0.7]
}
if (NDVI < 0.5) {
 return [0.2, 0.6, 0.3]
}
if (NDVI < 0.7) {
 return [0.5, 0.8, 0.2]
}
else {
 return [1, 0.4, 0]
 } 
IDB - List of available Indices   
```
 
## Recommended Band Combinations
 

### False Color Urban Composite.

Highlights built-up areas, making them stand out from natural features 

return [B12, B11, B04];

### SWIR-NIR Composite

This combination is effective for distinguishing between different types of ground cover, including disturbed soil and built-up areas. 

return [B11, B08, B04];

### False Color Vegetation

This is used for vegetation analysis but can be useful to monitor non-vegetated areas

return [B08, B04, B03];
 

### Normalised Difference Vegetation Index

NDVI is used to identify areas of distrubed soil or vegetation and could help us spot FOBs 

```
var NDVI = index(B08, B04);
if (NDVI < 0.2) {
  return [0.6, 0.4, 0.2]; // Non-vegetated
}
else if (NDVI < 0.5) {
  return [0.2, 0.6, 0.2]; // Sparse vegetation
}
else {
  return [0.0, 0.4, 0.0]; // Dense vegetation
}
 
```
### Combination

// Calculate NDVI
var NDVI = index(B08, B04);
// Enhance built-up areas using SWIR and NIR
let builtUpArea = [B12, B11, B04];
// Combine NDVI with built-up area enhancement
if (NDVI < 0.2) {
    // Likely built-up or disturbed soil
    return [B12, B11, B04];
} else if (NDVI < 0.5) {
    // Sparse vegetation
    return [B08 * 0.8, B04 * 0.6, B03 * 0.6];
} else {
    // Dense vegetation
    return [B08 * 0.6, B04 * 0.4, B03 * 0.4];
}
 

## Tutorials and Other Related Materials

Vegetation Spectral Cheat Sheet

Remote Sensing Tutorials by the Canada Centre for Mapping and Earth Observation

A PDF tutorial on writing simple evalscripts for beginners: Custom scripts tutorial

A webinar on writing evalscripts for beginners: Custom Scripts, September 28, 2020

A webinar on multi-temporal scripts and data fusion: Multi-temporal Scripts and Data Fusion, March 3, 2021

A blog on good scripting practices: Custom Scripts: Faster, Cheaper, Better!, November 18, 2019

A blog post on color maps: PUCK - Perceptually Uniform Color Maps in Satellite Imagery, January 28, 2021

A blog post on sampleType: SampleType: what’s all the fuss about?, February 15, 2022

More blog posts and useful links can be found on our Sentinel Hub website.

Space Operations, UK Ministry of Defense https://assets.publishing.service.gov.uk/media/5a79ebebed915d6b1deb4519/SpacePrimerFinalWebVersion.pdf

Index of remote sensing formulas IDB - List of available Indices 
