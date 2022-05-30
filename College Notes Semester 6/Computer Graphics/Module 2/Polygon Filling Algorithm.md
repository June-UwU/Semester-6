## Polygon Filling Algorithm

This algorithm works by intersecting scanline with polygon edges and fills the polygon between pairs of intersections. The following steps depict how this algorithm works.

>
>Step 1 : Find out the Ymin and Ymax from the given polygon.
>

![[scan_line_algorithm.jpg]]

>
>Step 2 − ScanLine intersects with each edge of the polygon from Ymin to Ymax. Name each intersection point of the polygon. As per the figure shown above, they are named as p0, p1, p2, p3.
>

>
Step 3 − Sort the intersection point in the increasing order of X coordinate i.e. p0,p1p0,p1, p1,p2p1,p2, and p2,p3p2,p3.
>

>
>Step 4  − Fill all those pair of coordinates that are inside polygons and ignore the alternate pairs.
>


