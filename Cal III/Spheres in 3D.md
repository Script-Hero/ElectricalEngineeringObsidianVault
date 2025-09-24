#Cal-3 
## Finding planar intersections of spheres in the [[Three-Dimensional Coordinate System]]

- Intersections will be circles (slice of sphere)
General formula: 

1. 
2. $x^2-2hx+h^2+y^2-2ky+k^2+z^2-2lz+l^2=r^2$

---



**Ex 1:**  Find center and radius of $x^{2}_+ { y^{2}+z^{2_{+8x}-6y}+2z+17}=0$ 

1. convert into perfect squares:
$(x^{2}+ 8x + 16)+(y^2-6y+9)+(z^2+2z+1)=-17+16+9+1=9$
2. Simplify: $(x+4)^{2}+ (y-3)^{2}+ (z+1)^{2}= 9$
3. Solve:
	-  center : (-4, 3, -1) & radius=3=$\sqrt{9}$
---
**Ex 2:** Find equation of sphere w center (1,2,3) that touches x-y plane

1. $(x-1)^{2} + (y-2)^{2}+ (z-3)^{2}= r^2$
2. Recognize that xy-plane means $z=0$
3. Since the center of the sphere is at $z=3$ (given) we know the distance between center and plane must be at least 3 --> radius must be 3 ($r=3$)
4. so $(x-1)^{2} + (y-2)^{2}+ (z-3)^{2}= r^{2}=3^{2}=9$

---

**Ex 3:** Find the equation of the sphere w radius 3, center (1,4,3). What is the intersection of this sphere with the three coordinate planes?

1. Equation of this sphere must be $(x-1)^{2}+ (y-4)^{2}+ (z-3)^2=3^2=9$
2. Intersection w xy-plane: 
	1. Means $z=0$
	2. If we plug in $z=0$ our equation becomes $(x-1)^{2}+ (y-4)^{2}+ (-3)^2=9$ --> $(x-1)^{2}+ (y-4)^{2} =0$
	3. This equation has solutions (specifically at $x=1$ and $y=4$) so **the sphere touches the xy-plane**
3. Intersection w xz-plane:
	1. Plug in $y=0$
	2. $(x-1)^{2}+ (16)^{2}+ (z-3)^2=3^2=9$ --> $(x-1)^{2}+ (z-3)^2=3^2=-7$
	3. This equation has no solution (you cannot have a circle with negative radius), so **the sphere does not intersect with the xz-plane**
4. Intersection with yz-plane:
	1. Plug in $x=0$
	2. $(-1)^{2}+ (y-4)^{2}+ (z-3)^2=3^2=9$ --> $(y-4)^{2}+ (z-3)^2=8$
	3. This equation has solutions, therefore **the sphere intersects with the yz-plane**
---

