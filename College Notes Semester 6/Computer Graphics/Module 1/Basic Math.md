## Lines And Basic Properties

The Cartesian slope-intercept equation for a straight line is:

$y = m * x + b$   (3-1)

with rn representing the slope of the line and b as they intercept. Given that the two endpoints of a he segment are speafied at positions (x,, y,) and (x, yJ, as shown in Fig. 3-3, we can determine values for the slope rn and y intercept b with the following calculations:

$m = \frac {y_{2} - y_{1}} {x_{2} - x_{1}}$ (3-2)

$b =y_{1} -m * x_{1}$ (3-3)

Algorithms for displaying straight hes are based on the line equation 3-1 and the calculations given in Eqs. 3-2 and 3-3. For any given x interval Ax along a line, we can compute the corresponding y interval from ~4.3-2 as

$\Delta y = m * \Delta x$  (3-4)

Similarly, wecan obtain the x interval $\Delta$x corresponding to a specified $\Delta$y as

$\Delta x = \frac{\Delta y}{m}$ (3-5)

## Circles And Basic Properties
A circle is defined as the set of points that are all at a given distance r from a center position $(x_{c}, y_{c})$ (Fig. 3-12). This distance relationship is expressed by the Pythagorean theorem in Cartesian coordinates as

$(x - x_{c})^2 - (y - y_{c})^2 = r^2$  (3-24)

![[Circle.png]]

We could use this equation to calculate the position of points on a circle circumference by stepping along the x axis in unit steps from $x_{c} - r$ to $x_{c} + r$ and calculating the corresponding y values

$y = y_{c} +/-  (r^2 - (x_{c} - x)^2)^-1$

But this is not the best method for generating a circle.the spacing between plotted pixel positions is not uniform, as demonstrated in Fig. 3-13.


![[circle eqn space.png]]

Another way to eliminate the unequal spacing shown in Fig. 3-13 is to calculate points along the circular boundary using polar coordinates r and 8 (Fig. 3-12). Expressing the circle equation in parametric polar form yields the pair of equations

$x = x_{c} + r \cos(\theta)$
$y = y_{c} + r \sin(\theta)$

When a display is generated with these equations using a fixed angular step size, a circle is plotted with equally spaced points along the circumference. The step size chosen for $\theta$ depends on the application and the display device. Larger angular separations along the circumference can be connected with straight line segments to approximate the circular path. For a more continuous boundary on a raster display, we can set the step size at 1/r.
This plots pixel positions that are approximately one unit apart. 

Computation can be reduced by considering the symmetry of circles. The shape of the circle is similar in each quadrant. We can generate the circle section in the second quadrant of the xy plane by noting that the two circle sections are symmetric with respect to they axis. quadrants can be obtained from sections in the first and second quadrants by considering symmetry about the x axis. We can take this one step further and note that there is als0 symmetry between octants. Circle sections in adjacent octants within one quadrant are symmetric with respect to the 45 degree line dividing the two octants


![[Circle Octants.png]]

