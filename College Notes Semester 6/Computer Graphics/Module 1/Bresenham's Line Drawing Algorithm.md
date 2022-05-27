# Bresenham's Line Drawing Algorithm
we- first consider the scan-conversion process for lines with positive slope less than 1. Pixel positions along a line path are then determined by sampling at unit x intervals. Starting from the left end point $(x_{0}, y_{0})$ of a given line, we step to each successive column (x position) and plot the pixel whose scan-line y value is closest to the line path. Figure 3-7 demonstrates the k th step in this process. Assuming we have determined that the pixel at $(x_{k}, y_{k})$ is to be displayed, we next need to decide which pixel to plot in column $x_{k+1}$,. Our choices are the pixels at positions $(x_{k+l}, y_{k})$ and $(x_{k+1}, y_{k+l})$. At sampling position $x_{k+1}$, we label vertical pixel separations from the mathematical line path as d, and d2 (Fig. 3-8). They coordinate on the mathematical line at pixel column position $x_{k+1}$ is calculated as

$y = m(x_{k} + 1) + b$

Then

$d = y - y_{k}$
   $= m(x_{k} + 1) + b y_{k}$

and

$d_{2} = (y_{k} + 1) - y$
    $= y_{k} + 1 - m(x_{k} + 1) - b$

The difference  between these two seperations is 

$d_{1} - d_{2} = 2m(x_{k} + 1) - 2y_{k} + 2b - 1$  (3-11)

A decision parameter $p_{k}$ for the kth step in the line algorithm can be obtained by rearranging Eq. 3-11 so that it involves only integer calculations. We accomplish this by substituting $m = \frac {\Delta y}{\Delta x}$, where $\Delta y$ and $\Delta x$ are the vertical and horizontal separations of the endpoint positions, and defining :

$p_{k} = \Delta x(d_{1} - d_{2})$
     $=2 \Delta y * x_{k} - 2 \Delta x * y_{k} + c$ (3-12)

The sign of p, is the same as the sign of $d_{1} - d_{2}$, since $\Delta x > 0$ for our example. Parameter c is constant and has the value $2 \Delta y + \Delta x(2b - 1)$, which is independent of pixel position and will be eliminated in the recursive calculations for $p_{k}$. If the pixel at $y_{k}$ is closer to the line path than the pixel at $y_{k + 1}$ (that is, $d_{1} < d_{2}$), then decision parameter $p_{k}$ is negative. In that case, we plot the lower pixel; otherwise, we plot the upper pixel.

Coordinate changes along the line occur in unit steps in either the x or y directions. Therefore, we can obtain the values of successive decision parameters using incremental integer calculations. At step k + 1, the decision parameter is evaluated from Eq. 3-12 as

$p_{k + 1} =  2 \Delta y * x_{k + 1} - 2 \Delta x * y_{k + 1} + c$

Subtracting Eq. 3-12 from the pding equation, we have

$p_{k + 1} - p_{k} = 2 \Delta y(x_{k + 1} - x_{k}) - 2 \Delta x(y_{k + 1} - y_{k})$

But $x_{k+1}$ = $x_{k}$ + 1, so that

$p_{k + 1} = p_{k} + 2 \Delta y - 2 \Delta x(y_{k + 1} - y_{k})$ (3-13)

where the term $y_{k+1} - y_{k}$ is either 0 or 1, depending on the sign of parameter $p_{k}$. This recursive calculation of decision parameters is performed at each integer x position, starting at the left coordinate endpoint of the line. The first parameter, $p_{0}$ is evaluated from Eq. 3-12 at the starting pixel position $(x_{0}, y_{0})$ and with m evaluated as $\Delta y / \Delta x$:

$p_{0} = 2 \Delta y - \Delta x$

```
Bresenham's Line Drawing Algorithm for |m| < 1
	1. Input the twoline endpoints and store the left endpoint in (x0, y0) 
	2. Load (x0, y0) into the frame buffer; that is, plot the first point. 
	3. Calculate constants dx, dy, 2dy, and 2dy - 2dx, and obtain the starting 
	    value for the decision parameter as 
			p(0) = 2dy - dx 
	4. At each xk along the line, starting at k = 0, perform the following test: 
	   If Pk < 0, the next point to plot is (xk + 1, yk) and 
	   
	   P(k+1) = P(k) + 2dy 
	   
	   Otherwise, the next point to plot is (x(k) + 1, y(k) + 1) and 
	   
	   p(k+1) = p(k) + 2dy - 2dx 
	5. Kepeat step 4 Ax times.
```


```
//C-Example

void linearbres (int xa, int ya, int xb, int yb) {
	int dx = abs (xa - xb), dy = abs (ya - yb); 
	int p = 2 * (dy - dx); 
	int twoDy = 2 * dy, twoDyDx = 2 * (dy - Ax); 
	int x, y, xEnd: 
	
	/* Determine which point to use as start, which as end */ 
	
	if (xa > xb) 
	{ 
		x = xb; 
		y = yb; 
		xEnd = xa; 
	}
	else
	{
		x = xa; 
		y = ya; 
		xEnd = xb;
	}
	
	setpixel (x, y); 
	while (x < xEnd) 
	{ 
		x++; 
		if (p < 0) 
		{
			p += twoDy;
		} 
		else 
		{
			y++;
			p += twoDyDx;
		} 
		setpixel (x, y);
	}
}

```


