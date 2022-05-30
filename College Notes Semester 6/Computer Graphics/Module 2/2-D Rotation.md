## 2-D Rotation

**Rotation** is a type of transformation that is very often used in computer graphics and image processing. Rotation is a process of rotating an object concerning an angle in a two-dimensional plane.

It is a process of changing the angle of the object which can be clockwise or anticlockwise, while we have to specify the angle of rotation and rotation point. A rotation point is also called a pivot point.

There are two types of rotations according to the direction of the movement of the object. These are:

-   Anti-clockwise rotation
-   Clockwise rotation

The positive value of the rotation angle rotates an object in an anti-clockwise direction while the negative value of the rotation angle rotates an object in a clockwise direction. When we rotate any object, then every point of that object is rotated by the same angle. For example, a straight line is rotated by the endpoints with the same angle and the line is re-drawn between the new endpoints. Also, the polygon is rotated by shifting every vertex with the help of the same rotational angle. Same for circle also, it can be obtained by center position by the specified angle.

Let's now consider a point object O which has to be rotated from one angle to another.

-   Initial co-ordinates of the object $O = (X_{old}, Y_{old})$
-   Initial angle of the object O with respect to origin = Φ
-   Rotation angle = θ
-   New co-ordinates of the object O after rotation $= (X_{new}, Y_{new})$

![[rotation-1.jpg]]

In order to rotate an object, we need to rotate each vertex of the figure individually. More clearly let us assume a point **P**, on rotating a point **P(x, y)** by an angle **A** about the origin we get a point **P' (x', y')**. The calculation of values of **x'** and **y'** are as follows,

We know that,
>
$x   = r cosB, y = r sinB$
>
$x'  = r cos ( A + B)$
	 $= r ( cosA cosB – sinA sinB )$ 
     $= r cosB cosA – r sinB sinA$
     $= x cosA – y sinA$
>
$y'  = r sin ( A + B )$
	 $= r ( sinA cosB + cosA sinB )$  
     $= r cosB sinA + r sinB cosA$ 
     $= x sinA + y cosA$
>

It's representation in matrix form will be as follows,

![[rotat2d.PNG]]
