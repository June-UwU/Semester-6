# Raster Scan Display
**Raster Scan Displays** are most common type of graphics monitor which employs CRT. It is based on television technology. In raster scan system electron beam sweeps across the screen, from top to bottom covering one row at a time.A pattern of illuminated pattern of spots is created by turning beam intensity on and off as it moves across each row. A memory area called refresh buffer or frame buffer stores picture definition. This memory area holds intensity values for all screen points. Stored intensity values are restored from frame buffer and painted on screen taking one row at a time.Each screen point is referred to as pixels.

In raster scan systems refreshing is done at done at a rate of 60-80 frames per second. Refresh rates are also sometimes described in units of cycles per second / Hertz (Hz). At the end of each scan line, electron beam begins to display next scan line after returning to left side of screen. The return to the left of screen after refresh of each scan line is known as **_horizontal retrace_** of electron beam. At the end of each frame electron beam returns to top left corner and begins the next frame , This is **_Vertical retrace_**.


![[Retraces and Raster Scan Display.png]]

---
# Additional Info
## **Raster-Scan Display Processor:**  
An important function of display process is to digitize a picture definition given in an application program into a set of pixel-intensity values for storage in refresh buffer. This process is referred to as **scan conversion**. The purpose of display processors is to relieve the CPU from graphics jobs.

Display processors can perform various other tasks like: creating different line styles, displaying color areas, etc. Typically display processors are utilized to interface input devices, such as mouse, joysticks.

![[Random Scan Processors.jpg]]

>**ADVANTAGES:**
>
>-   Real life images with different shades can be displayed.
>-   Color range available is bigger than random scan display.

>**DISADVANTAGES:**
>
>-   Resolution is lower than random scan display.
>-   More memory is required.
>-  Data about the intensities of all pixel has to be stored.

#module1 