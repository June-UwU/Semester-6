# Random-Scan Display
In **Random-Scan Display** electron beam is directed only to the areas of screen where a picture has to be drawn. It is also called vector display, as it draws picture one line at time. It can draw and refresh component lines of a picture in any specified sequence.

The number of lines regulates refresh rate on random-scan displays. An area of memory called **refresh display files** stores picture definition as a set of line drawing commands. The system returns back to first-line command in the list, after all the drawing commands have been processed. High-quality vector systems can handle around 100,00 short lines at this refresh rate. Faster refreshing can burn phosphor. To avoid this every refresh cycle is delayed to prevent refresh rate greater than 60 frames per second.


![[2000px-Bitmap_vs_vector.svg.png]]
---
# Additional Info

## Random-Scan Display Processors:  
Input in the form of an application program is stored in the system memory along with graphics package. Graphics package translates the graphic commands in application program into a display file stored in system memory. This display file is then accessed by the display processor to refresh the screen. The display processor cycles through each command in the display file program. Sometimes the display processor in a random-scan is referred as _Display Processing Unit / Graphics Controller_.

The structure of a simple random scan is shown below:

![[Random Scan Processors.jpg]]

> **Advantages**
> 
>-  Higher resolution as compared to raster scan display.
> -   Produces smooth line drawing.
> -   Less Memory required.
>  

>**DISADVANTAGES:**
>
>-   Realistic images with different shades cannot be drawn.
>-   Colour limitations.

#module1


