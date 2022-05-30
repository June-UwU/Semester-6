## Flood Fill Algorithm

Sometimes we come across an object where we want to fill the area and its boundary with different colors. We can paint such objects with a specified interior color instead of searching for particular boundary color as in boundary filling algorithm.

Instead of relying on the boundary of the object, it relies on the fill color. In other words, it replaces the interior color of the object with the fill color. When no more pixels of the original interior color exist, the algorithm is completed.

Once again, this algorithm relies on the Four-connect or Eight-connect method of filling in the pixels. But instead of looking for the boundary color, it is looking for all adjacent pixels that are a part of the interior.

![[flood_fill_algorithm.jpg]]

There are two types of fill techniques that are used with this algorithm

[[4-Connected Polygon]]
[[8-Connected Polygon]]


>1. 4-Connected Flood fill Subroutine
>
>void flood_fill(int x , int y , int new_col ,int old_col)
>{
>	if(getpixel(x,y) == old_col)
>	{
>		putpixel(x,y,newcol); //make it the new color
>		flood_fill(x + 1 ,y,new_col,old_col);
>		flood_fill(x - 1 ,y,new_col,old_col);
>		flood_fill(x,y + 1 ,new_col,old_col);
>		flood_fill(x ,y -1 ,new_col,old_col);
>	}
>}


> 2. 8-Connected Flood fill Subroutine
>
>void flood_fill(int x , int y , int new_col ,int old_col)
>{
>	if(getpixel(x,y) == old_col)
>	{
>		putpixel(x,y,newcol); //make it the new color
>		flood_fill(x + 1 ,y,new_col,old_col);
>		flood_fill(x + 1 ,y + 1,new_col,old_col);
>		flood_fill(x - 1 ,y,new_col,old_col);
>		flood_fill(x - 1 ,y + 1,new_col,old_col);
>		flood_fill(x ,y + 1 ,new_col,old_col);
>		flood_fill(x + 1 ,y - 1,new_col,old_col);
>		flood_fill(x ,y -1 ,new_col,old_col);
>		flood_fill(x - 1 ,y - 1,new_col,old_col);
>	}
>}