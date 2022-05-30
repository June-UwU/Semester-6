## Boundary Fill Algorithm

The boundary fill algorithm works as its name. This algorithm picks a point inside an object and starts to fill until it hits the boundary of the object. The color of the boundary and the color that we fill should be different for this algorithm to work.

In this algorithm, we assume that color of the boundary is same for the entire object. The boundary fill algorithm can be implemented by 4-connected pixels or 8-connected pixels.

![[boundary_fill.png]]

There are two types of fill techniques that are used with this algorithm

[[4-Connected Polygon]]
[[8-Connected Polygon]]


>1. 4-Connected Boundary fill Subroutine
>
>void flood_fill(int x , int y , int new_col ,int bound_col)
>{
>	if(getpixel(x,y) != bound_col)
>	{
>		putpixel(x,y,newcol); //make it the new color
>		flood_fill(x + 1 ,y,new_col,bound_col);
>		flood_fill(x - 1 ,y,new_col,bound_col);
>		flood_fill(x,y + 1 ,new_col,bound_col);
>		flood_fill(x ,y -1 ,new_col,bound_col);
>	}
>}


> 2. 8-Connected Boundary fill Subroutine
>
>void flood_fill(int x , int y , int new_col ,int old_col)
>{
>	if(getpixel(x,y) == old_col)
>	{
>		putpixel(x,y,newcol); //make it the new color
>		flood_fill(x + 1 ,y,new_col,bound_col);
>		flood_fill(x + 1 ,y + 1,new_col,bound_col);
>		flood_fill(x - 1 ,y,new_col,bound_col);
>		flood_fill(x - 1 ,y + 1,new_col,bound_col);
>		flood_fill(x ,y + 1 ,new_col,bound_col);
>		flood_fill(x + 1 ,y - 1,new_col,bound_col);
>		flood_fill(x ,y -1 ,new_col,bound_col);
>		flood_fill(x - 1 ,y - 1,new_col,bound_col);
>	}
>}