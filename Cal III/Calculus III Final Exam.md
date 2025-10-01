
# Flow:

Path integral: $\int^{a}_{b}f(t)\cdot|\vec{r}'(t)|dt$
- the function is given, you just convert to $t$, the path gives you the bounds only
	
Surface area: $\int\int|\vec{r}_{u}\times\vec{r}_{v}|dudv$
- the function is given, you convert to a function of $u$ and $v$, the bounds are given by the "constraint shape"
- if there's a function involved it could be $\int\int\mathbf{F}\cdot|\vec{r}_{u}\times\vec{r}_{v}|$
Divergence or Finding Flux (probably also div. theorem): $\int\int_{S}\mathbf{F} =\int\int\int div(\mathbf{F})$
- Makes a surface integral easier for ugly [[Vectors]]. Bounds come from the constraint shape

Work: $\int \vec{F(t)} \cdot \vec{r'(t)}$ 
- Where $r$ is the path and $F$ is given. The bounds of the integral also come from the path

When your path integral is too hard, use Stoke's Theorem: $\int_{C}\mathbf{F}=\int\int_{S}curl(\mathbf{F})$

---

## 14.7

Local and absolute extrema.

## 16.1 Vector Fields 
A vector field is a function whose domain is a set of points in $\mathbb{R^{2}}$ or  $\mathbb{R^{3}}$ whose range is a set of [[Vectors]].
- Gradient of a vector field $\nabla f(x,y)=f_{x}(x,y)i+ f_{y}(x,y)j$

## 16.2 Line Integrals
If a function of 2 variables $f$ is defined on a smooth curve $C$ given by $r(t)=(x(t), y(t))$ then the line integral of $f$ along $C$ is
$\int_{C}f(x,y)ds=\lim_{x\to \infty}\sum\limits_{i=1}^{n}f(x_{i},y_{i})\Delta s_{i}$

- arc length $s=s(t)=\int_{a}^{t}|r'(u)|dt$

**The important definition:** $$\int_{C}f(x,y)ds=\int_{a}^{b}f(x(t),y(t))\cdot|r'(t)|dt$$
- for $a\leq t \leq b$ 
- In 3 dimensions it's $\int_{C}f(x,y)ds=\int_{a}^{b}f(x(t),y(t),z(t))\cdot|r'(t)|dt$




## 16.3 Fundamental Theorem For Line integrals

- Ignore that annoying ass definition, it's literally just "$\int \nabla \vec{r}(t)=\vec{r}(t)$" the normal "integral of a derivative of $f$ is $f$ ".

**Definition: ***Let $C$ be a smooth curve given by the vector function $r(t)$ for $a\leq t\leq b$. Let $f$ be a differentiable function of 2 or 3 variables whose gradient vector $\nabla f$ is continuous on $C$. Then:*
$$
\int_{C}\nabla f \cdot dx =f(r(b))-f(r(a))
$$

- Remembering that $\int_{C}f(x,y)ds=\int_{a}^{b}f(x(t),y(t))\cdot|r'(t)|dt$

- Some stuff here with simply connected regions, independent paths, not recorded yet because I don't know if it's important 
## 16.4 Green's Theorem
- Connects line integral to the double integral (area integral)
$\oint(Ldx + Mdy)=\int\int_{D}(\frac{\delta M}{\delta x}-\frac{\delta L}{\delta y})dA$
	- Where $L$ and $M$ are functions of $x$ and $y$

## 16.5 Curl & Divergence
Given a 3D vector function $F=<P,Q,R>$ where the partial derivative of all 3 variables exist, ***curl*** is defined as:
	*Curl* $F$ = $\nabla \times F = \begin{bmatrix}i  & j & k\\ \frac{\delta}{\delta x} & \frac{\delta}{\delta y} & \frac{\delta}{\delta z}\\ P & Q&R\end{bmatrix}$ 
- If $F$ is conservative, the curl is 0, and if Curl is 0, then F is conversative

	*Divergence* $F=\nabla\cdot F=\frac{\delta P}{\delta x}+\frac{\delta Q}{\delta y}+\frac{\delta R}{\delta z}$

## 16.6 Parametric Surfaces & Areas
- Parametric function such that $r(u,v)=x(u,v)i+y(u,v)j+z(u,v)k$
Surface area function $Area(S)=\int\int_{D}|r_{u}\times r_{v}|dudv$

- There's a special case where $z=f(x,y)$ so that we can express the entire parametric equation only in terms of $x$ and $y$. Then $|r_{x}\times r_{y}|=\sqrt{1+f_{x}^{2}+f_{y}^{2}}$
- 
## 16.7 Surface Integrals

Surface integral $\int\int_{S}f(x,y,z)dS = \int_{D}\int f(r(u,v))|r_{u}\times r_{v}|d_{A}$ 

Suppose a thin sheet, such as aluminum foil, has the shape of a surface S, and the density of a function $\rho(x,y,z)$ then the total mass of the sheet is $\int \int_{S}\rho(x,y,z) dS$  

- Note that we can parameterize a sphere with *radius* $\rho$ as $r(\phi,\theta)=<\rho\sin\phi\cos\theta,\rho\sin\phi\sin\theta,\rho\cos\phi>$ 

**Oriented Surfaces**
- analogous to oriented curves
- since surfaces are 2 sided we must have an *orientation* of the surface
- usually we choose **positive** orientation meaning **positive $k$ component**
- for ***closed*** surfaces the convention is to have the normal vector that points **outward** from the surface.
## 16.8 Stokes' Theorem
$\int_{C} F\cdot dr = \int\int_{S}curl\mathbf{F}\cdot dS=\int\int_{D}curl\mathbf{F}(r(u,v))\cdot (r_{u}\times r_{v})dA$
- allows us to compute a line integral over a closed curve in space

## 16.9 The Divergence Theorem
A surface integral over a **closed surface** $S$ can be evaluated as a [[Triple Integral]] over the volume enclosed by the surface.

**Divergence Theorem** Let $E$ be a simple solid region whose boundary surface $S$ has positive (outward) orientation. Let $\mathbf{F}$ be a vector field whose component function have continuous partial derivatives on an open region that contains $E$. Then:
$$
\int\int_{S}\mathbf{F}\cdot dS = \int\int_{E}\int\ div\mathbf{F}dV
$$
- If $C$ is the enclosed boundary curve of a surface $S$ that is also a closed surface, then $S$ must enclose a volume, $E$. Assuming positive orientation, these three integrals are equivalent:
$$
\int_{C}\mathbf{F}\cdot dr=\int\int_{S}curl \mathbf{F}\cdot dS = \int\int_{E}\int div(curl\mathbf{F})dV
$$