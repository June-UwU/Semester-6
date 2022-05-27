# DDA Algorithm 

The digital drflerential analyzer (DDA) is a scan-conversion line algorithm based on calculating either $\Delta$ y or $\Delta$ x.We sample the line at unit intervals in one coordinate and determine corresponding integer values nearest the along line path for the other coordinate.


![[ddafig.png]]


Consider first a line with positive slope, as shown in Fig. 3-4. If the slope is less than or equal to 1, we sample at unit x intervals ($\Delta x = 1$) and compute each successive y value as

$y_{k + 1} = y_{k} + m$  (3-6)

Subscript k takes integer values starting from 1, for the first point, and increases by 1 until the final endpoint is reached. Since m can be any real number between 0 and 1, the calculated y values must be rounded to the next integer. 

For lines with a positive slope greater than 1, we reverse the roles of *x* and *y*. That is, we sample at unit y intervals ($\Delta y = 1$) and calculate each succeeding x value as

$x_{k+1} = x_{k} + \frac{1}{m}$ (3-7)

Equations 3-6 and 3-7 are based on the assumption that lines are to be processed from the left endpoint to the right endpoint (Fig. 3-3). If this processing is reversed, so that the starting endpoint is at the right, then either we have ($\Delta x = -1$) and

$y_{k+1} = y_{k} - m$ (3-8)

or (when the slope is greater than I) we have $\Delta y = -1$ with

$x_{k+1} = x_{k} - \frac{1}{m}$ (3-9)

```
//C-Example

#define ROUND(x) ((int)(x))
void lineDDA (int xa, int ya, int xb, int yb) 
{ 
	int dx = xb - xa, dy = yb - ya, steps, k; 
	float xrncrement, yIncrement, x = xa, y = ya; 
	if (abs (dx) > abs (dyl) 
	{
		steps = abs (dx) ; 
	}
	else
	{ 
		steps = abs dy);
	} 
	xIncrement = dx i (float) steps;
	yIncrement = dy 1 (float) steps;
	setpixel (ROUND(x), ROUND(y));
	for (k=O; k <= steps; k++)
	{
		x += xIncrement;
		y += yIncrement;
		setpixel(ROUND(x), ROUND(y));
	} 
}
```

