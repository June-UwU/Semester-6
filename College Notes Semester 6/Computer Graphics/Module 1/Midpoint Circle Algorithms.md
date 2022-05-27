# Midpoint Circle Algorithm

As in the raster line algorithm, we sample at unit intervals and determine the closest pixel position to the specified circle path at each step. For a given radius r and screen center position $(x_{c}, y_{c})$, we can first set up our algorithm to calculate pixel positions around a circle path centered at the coordinate origin (0,0). Then each calculated position (x, y) is moved to its proper screen position by adding $x_{c}$ to x and $y_{c}$ to y. Along the circle section from x = 0 to x = y in the first quadrant, the slope of the curve varies from 0 to -1. Therefore, we can take unit steps in the positive x direction over this octant and use a decision parameter to determine which of the two possible y positions is closer to the circle path at each step. Positions ih the other seven octants are then obtained by symmetry. To apply the midpoint method, we define a circle function:

$\begin{align*} f_{circle}(x,y) = x^2 + y^2 - r^2 \end{align*}$

Any point (x, y) on the boundary of the circle with radius r satisfies the equation $f_{circle}(x,y) = 0$. If the point is in the interior of the circle, the circle function is negative. And if the point is outside the circle, the circle function is positive. To summarize, the relative position of any point (x, y) can be determined by checking the sign of the circle function

Assuming we have just plotted the pixel at $(x_{k}, y_{k})$, we next need to determine whether the pixel at position $(x_{k + 1}, y_{k})$ or the one at position $(x_{k + 1}, y_{k - 1})$ is closer to the circle. Our decision parameter is the circle function evaluated at the midpoint between these two pixels:

$p_{k} = f_{circle}(x_{k} + 1,y_{k} - \frac{1}{2})$
			  $= (x_{k} + 1)^2 + (y_{k} - \frac{1}{2})^2 - r^2$

If $p_{k}$ < 0, this midpoint is inside the circle and the pixel on scan line $y_{k}$ is closer to the circle boundary. Otherwise, the midposition is outside or on the circle boundary, and we select the pixel on scanline $y_{k} - 1$. Successive decision parameters are obtained using incremental calculations


```
Midpoint Circle Algorithm

	1. Input radius r and circle center (xc,  yc), and obtain the first point on 
       the circumference of a circle centered on the origin as 

		(x0,y0) = (0,r)
	
	2. calculate the initial value of the decision parameter as 
		
		p0 = 5/4 - r	
	
	3. At each xk position, starting at k = 0, perform the following test:
	   If pk C < 0, the next point along the circle centered on (0,O) is (xk+1,yk) 
       and

		p(k+1) = p(k) + 2x(k+1) + 1
		
	    Otherwise, the next point along the circle is (xk + 1, yk - 1) and where 
        2x(k+1) = 2x(k) + 2 and 2y(k+1), = 2y(k) - 2. 
    
	4. Deterrnine symmetry points in the other seven octants. 
    
	5. Move each calculated pixel position (x, y) onto the circlar path centered on 
    (xc, yc) and plot the coordinate values: 
    
	    x=x+x(c), y=y+y(c) 
    
	6. Repeat steps 3 through 5 until x r y.
```


```
C-Example

void circleMidpoint (int xCenter, int yCenter, int radius) 
{ 
	int x = 0; 
	int y = radius; 
	int p = 1 - radius; 
	
	void circlePlotPoints (int, int, int, int); 
	
	/* Plot first set of points */
	
	circlePlotPoints (xCenter. yCenter, x, y); 
	while (x < y) 
	{ 
		x++ ; 
		if (P < O) 
		{
			p+= 2 * x + 1 
		}
		else 
		{ 
			Y--;
			p += 2 * (x - Y) + 1; 
		}
		circlePlotPoints(xCenter,yCenter,x,y);
	}
}

void circlePlotPoints(int xCenter, int yCenter, int x, int yl)
{
	setpixel (xCenter + x, $enter + y); 
	setpixel (xCenter - x. $enter + yl; 
	setpixel (xCenter + x, $enter - y); 
	setpixel (xCenter - x, $enter - y); 
	setpixel (xCenter + y, $enter + x); 
	setpixel (xCenter - y, $enter + x); 
	setpixel (xCenter t y, $enter - x); 
	setpixel (xCenter - y, $enter - x);
} 
```