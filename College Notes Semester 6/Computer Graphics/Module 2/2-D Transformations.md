## 2-D Transformations

[[2-D Translation]] : This translates the point with the distance can be specified
[[2-D Rotation]] : This rotates point with $\theta$
[[2-D Scaling]] : Scales the points by a scale factor
[[2-D Reflection]] : reverses the direction of one or more coordinate
[[2-D Shearing]] : 
[[2-D Composite Transformation]] : Combination of transformations
[[2-D Homogenus Transformation]] : 


>
>General structures that will be used in the above transformation
>
```
template <typename T>
struct vec2d
{
	T x;
	T y;
};

template <typename T>
struct mat2d
{
	T x0,x1;
	T y0,y1;
};

using vec2d_f = vec2d<float>;
using mat3d_f = mat2d<float>;

```
