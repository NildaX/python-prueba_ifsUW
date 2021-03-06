# Prueba ifsUW
_Provides a 2D interactive visualisation of the spaxels and spectra of a 3D cube for visualise, manipulate, and analyse integral field spectroscopy (IFS) data regardless of the original instrument_
### Installation
For install the package of Prueba ifsUW:
```
pip install prueba_ifsUW
```
Depending of the version, could be:
```
pip3 install prueba_ifsUW
```

For show the window of prueba_ifsUW, in any terminal of python run the next code:
```
from prueba_ifsUW import *
x = prueba_ifsUW() 
```
### Description
The program accept FITS files with extensions:
- .fits
- .fits.gz

The fits files should have projection of RA and DEC or degrees.
The program displays one windows with the next panels: 
- The file explorer to select a file to run with the program
- Two panels to show the name of the object and the state of the explorer (on, off, select a spaxel for be the center of the integrated region and show the integrated spectrum)
- Text area to show messsages of the program like the dimensions of the cube, filters used, instruccions, errors, etc.
- The area for extract region have entry for the radius, button for draw the circle, buttons for create files when previusly drew the circle and show the integrated spectrum of the spaxels inside the circle,the functions permit create three files:
```
Extracted FITS:  
NAMEFITS_rscube_circle_centerx_centery.fits (Extracted FITS of the selected spaxels)
Integrated ASCII:  
NAMEFITS.spectrum_centerx_centery.txt (Integrated spectrum in ASCII format)
Espectrum FITS:  
NAMEFITS.spectrum_centerx_centery.fits (Integrated spectrum in FITS format)
```
- Under the area of extract region shows the options to change display axis in projections in RA-DEC and offsets and the area for mark wavelength in the format of numbers separated  by a coma and the function to reset the marks.  
Example:  400,500  
With the conditions:  
minimum value of the array lambda <= x <= maximum value of the array lambda
- The area of display content the functions to change the Color map (or invert it) of the image FITS and change the Filter.
- The area to change axis x (Wavelength) and y(Flux) of the spectrum graph, with the next conditions:  
For flux range:  
minimum value < maximum value  
Negative values are accepted.  
For Wavelength range:  
minimum value of array lambda <= minimum value < maximum value <= maximum value of array lambda  
Negative values are not accepted.
- The area to show the information about the spaxel, if the WCS information is included in the FITS header it shows the coordinates of the spaxel in sexagesimal and degree units. For example:
```
Spaxel             ID                 RA                        DEC 
[ 46 , 23 ]       1794        12 h  41 m  52.596600 s      41 d 16 m 15.005 s  

  RA-deg         DEC-deg
 190.469         41.2708
```
- And if not included:
```
   Spaxel          ID
[ 46 , 23 ]       1794
```
- The area to change value of the band used for the filter, this could be change directly get the number or moving the scale bar, they have one condition:  
minimum value of array lambda <= band <= maximum value of array lambda  
This function affect the spectrum graph and the image.
- For last the area to the spectrum graph and the area for display the FITS image.  
The area of the image change the spectrum graph depending on what spaxel the mouse is on, or if the explorer is enabled.  
The spectrum graph show the array lambda on the x axis and the information about the spaxel of the cube in the y axis 
