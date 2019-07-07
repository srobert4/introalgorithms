Course Notes
================

Notes for the MIT Open Courseware version of Introduction to Algorithms,
2011. Class homepage found
[here](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-006-introduction-to-algorithms-fall-2011/index.htm)

## Unit 1: Introduction

**Reading**: 1, 3, D.1, [Python cost
model](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-006-introduction-to-algorithms-fall-2011/readings/python-cost-model)

### Asymptotic notation

  - Asymptotic notation applies to functions not to algorithms
  - When applied to running time, need to specify *which* (worst-case,
    all inputs)

#### ![\\Theta](https://latex.codecogs.com/png.latex?%5CTheta "\\Theta")-notation

**Definition**

For a given function
![g(n)](https://latex.codecogs.com/png.latex?g%28n%29 "g(n)"), we denote
![\\Theta(g(n))](https://latex.codecogs.com/png.latex?%5CTheta%28g%28n%29%29
"\\Theta(g(n))") the *set of functions*

  
![
\\Theta(g(n)) = \\{f(n) : \\text{ there exist positive constants } c\_1,
c\_2,\\text{ and } n\_0 
\\text{ such that } \\\\
0 \\leq c\_1g(n) \\leq f(n) \\leq c\_2g(n) \\text{ for all } n \\geq
n\_0\\}
](https://latex.codecogs.com/png.latex?%0A%5CTheta%28g%28n%29%29%20%3D%20%5C%7Bf%28n%29%20%3A%20%5Ctext%7B%20there%20exist%20positive%20constants%20%7D%20c_1%2C%20c_2%2C%5Ctext%7B%20and%20%7D%20n_0%20%0A%5Ctext%7B%20such%20that%20%7D%20%5C%5C%0A0%20%5Cleq%20c_1g%28n%29%20%5Cleq%20f%28n%29%20%5Cleq%20c_2g%28n%29%20%5Ctext%7B%20for%20all%20%7D%20n%20%5Cgeq%20n_0%5C%7D%0A
"
\\Theta(g(n)) = \\{f(n) : \\text{ there exist positive constants } c_1, c_2,\\text{ and } n_0 
\\text{ such that } \\\\
0 \\leq c_1g(n) \\leq f(n) \\leq c_2g(n) \\text{ for all } n \\geq n_0\\}
")  

This definition requires that
![f(n)](https://latex.codecogs.com/png.latex?f%28n%29 "f(n)") is
*asymptotically nonnegative*.

In words, we write ![f(n) = \\text{ or } \\in
\\Theta(g(n))](https://latex.codecogs.com/png.latex?f%28n%29%20%3D%20%5Ctext%7B%20or%20%7D%20%5Cin%20%5CTheta%28g%28n%29%29
"f(n) = \\text{ or } \\in \\Theta(g(n))") if there exist positive
constants
![c\_1,c\_2,n\_0](https://latex.codecogs.com/png.latex?c_1%2Cc_2%2Cn_0
"c_1,c_2,n_0") such that at and to the right of
![n\_0](https://latex.codecogs.com/png.latex?n_0 "n_0"), the value of
![f(n)](https://latex.codecogs.com/png.latex?f%28n%29 "f(n)") always
lies between
![c\_1g(n)](https://latex.codecogs.com/png.latex?c_1g%28n%29 "c_1g(n)")
and ![c\_2g(n)](https://latex.codecogs.com/png.latex?c_2g%28n%29
"c_2g(n)").

If ![f(n) =
\\Theta(g(n))](https://latex.codecogs.com/png.latex?f%28n%29%20%3D%20%5CTheta%28g%28n%29%29
"f(n) = \\Theta(g(n))") then
![g(n)](https://latex.codecogs.com/png.latex?g%28n%29 "g(n)") is an
**asymptotically tight bound** for
![f(n)](https://latex.codecogs.com/png.latex?f%28n%29 "f(n)").

**Proving ![f(n) =
\\Theta(g(n))](https://latex.codecogs.com/png.latex?f%28n%29%20%3D%20%5CTheta%28g%28n%29%29
"f(n) = \\Theta(g(n))")**

*Example:*

Let ![f(n) = \\frac{1}{2}n^2
- 3n](https://latex.codecogs.com/png.latex?f%28n%29%20%3D%20%5Cfrac%7B1%7D%7B2%7Dn%5E2%20-%203n
"f(n) = \\frac{1}{2}n^2 - 3n"). To show ![f(n) =
\\Theta(n^2)](https://latex.codecogs.com/png.latex?f%28n%29%20%3D%20%5CTheta%28n%5E2%29
"f(n) = \\Theta(n^2)") we want to show that ![c\_1n^2 \\leq
\\frac{1}{2}n^2 - 3n \\leq
c\_2n^2](https://latex.codecogs.com/png.latex?c_1n%5E2%20%5Cleq%20%5Cfrac%7B1%7D%7B2%7Dn%5E2%20-%203n%20%5Cleq%20c_2n%5E2
"c_1n^2 \\leq \\frac{1}{2}n^2 - 3n \\leq c_2n^2") for all ![n \\geq
n\_0](https://latex.codecogs.com/png.latex?n%20%5Cgeq%20n_0
"n \\geq n_0") for some
![c\_1,c\_2,n\_0](https://latex.codecogs.com/png.latex?c_1%2Cc_2%2Cn_0
"c_1,c_2,n_0").

  
![
\\begin{aligned}
c\_1n^2 \\leq &\\frac{1}{2}n^2 - 3n \\leq c\_2n^2 \\\\
&\\text{ dividing by } n^2 \\text{ yields}\\\\
c\_1 \\leq &\\frac{1}{2} - \\frac{3}{n} \\leq c\_2
\\end{aligned}
](https://latex.codecogs.com/png.latex?%0A%5Cbegin%7Baligned%7D%0Ac_1n%5E2%20%5Cleq%20%26%5Cfrac%7B1%7D%7B2%7Dn%5E2%20-%203n%20%5Cleq%20c_2n%5E2%20%5C%5C%0A%26%5Ctext%7B%20dividing%20by%20%7D%20n%5E2%20%5Ctext%7B%20yields%7D%5C%5C%0Ac_1%20%5Cleq%20%26%5Cfrac%7B1%7D%7B2%7D%20-%20%5Cfrac%7B3%7D%7Bn%7D%20%5Cleq%20c_2%0A%5Cend%7Baligned%7D%0A
"
\\begin{aligned}
c_1n^2 \\leq &\\frac{1}{2}n^2 - 3n \\leq c_2n^2 \\\\
&\\text{ dividing by } n^2 \\text{ yields}\\\\
c_1 \\leq &\\frac{1}{2} - \\frac{3}{n} \\leq c_2
\\end{aligned}
")  

Solving the left and right inequalities gives ![c\_1 = \\frac{1}{14},
c\_2 = \\frac{1}{2}, n\_0
= 7](https://latex.codecogs.com/png.latex?c_1%20%3D%20%5Cfrac%7B1%7D%7B14%7D%2C%20c_2%20%3D%20%5Cfrac%7B1%7D%7B2%7D%2C%20n_0%20%3D%207
"c_1 = \\frac{1}{14}, c_2 = \\frac{1}{2}, n_0 = 7") as an acceptable
solution. We only need to show there exists one solution, although there
are infinitely many others.

*In general* for any polynomial ![f(n) = \\sum\_{i=0}^d
a\_in^i](https://latex.codecogs.com/png.latex?f%28n%29%20%3D%20%5Csum_%7Bi%3D0%7D%5Ed%20a_in%5Ei
"f(n) = \\sum_{i=0}^d a_in^i") where
![a\_i](https://latex.codecogs.com/png.latex?a_i "a_i") are constants
and ![a\_d \> 0](https://latex.codecogs.com/png.latex?a_d%20%3E%200
"a_d \> 0"), ![f(n) =
\\Theta(n^d)](https://latex.codecogs.com/png.latex?f%28n%29%20%3D%20%5CTheta%28n%5Ed%29
"f(n) = \\Theta(n^d)")

*Note* that a constant function is often denoted as
![\\Theta(1)](https://latex.codecogs.com/png.latex?%5CTheta%281%29
"\\Theta(1)").

**Proving ![f(n) \\neq
\\Theta(g(n))](https://latex.codecogs.com/png.latex?f%28n%29%20%5Cneq%20%5CTheta%28g%28n%29%29
"f(n) \\neq \\Theta(g(n))")**

*Example*

Let ![f(n)
= 6n^3](https://latex.codecogs.com/png.latex?f%28n%29%20%3D%206n%5E3
"f(n) = 6n^3"). To show that ![f(n) \\neq
\\Theta(n^2)](https://latex.codecogs.com/png.latex?f%28n%29%20%5Cneq%20%5CTheta%28n%5E2%29
"f(n) \\neq \\Theta(n^2)") we use contradiction. Suppose that
![c\_2](https://latex.codecogs.com/png.latex?c_2 "c_2") and
![n\_0](https://latex.codecogs.com/png.latex?n_0 "n_0") exist such that
![6n^3 \\leq
c\_2n^2](https://latex.codecogs.com/png.latex?6n%5E3%20%5Cleq%20c_2n%5E2
"6n^3 \\leq c_2n^2") for all ![n \\geq
n\_0](https://latex.codecogs.com/png.latex?n%20%5Cgeq%20n_0
"n \\geq n_0"). Dividing by
![n^2](https://latex.codecogs.com/png.latex?n%5E2 "n^2") yields ![n
\\leq
\\frac{c\_2}{6}](https://latex.codecogs.com/png.latex?n%20%5Cleq%20%5Cfrac%7Bc_2%7D%7B6%7D
"n \\leq \\frac{c_2}{6}") for all ![n \\geq
n\_0](https://latex.codecogs.com/png.latex?n%20%5Cgeq%20n_0
"n \\geq n_0") but this is impossible for arbitrarily large
![n](https://latex.codecogs.com/png.latex?n "n") since
![c\_2](https://latex.codecogs.com/png.latex?c_2 "c_2") is a constant.

#### ![O](https://latex.codecogs.com/png.latex?O "O")-notation

An asymptotic upper bound

**Definition**

  
![
O(g(n)) = \\{f(n) : \\text{ there exist positive constants } c \\text{
and } n\_0 \\text{ such that } \\\\
0 \\leq f(n) \\leq cg(n) \\text{ for all } n \\geq n\_0\\}
](https://latex.codecogs.com/png.latex?%0AO%28g%28n%29%29%20%3D%20%5C%7Bf%28n%29%20%3A%20%5Ctext%7B%20there%20exist%20positive%20constants%20%7D%20c%20%5Ctext%7B%20and%20%7D%20n_0%20%5Ctext%7B%20such%20that%20%7D%20%5C%5C%0A0%20%5Cleq%20f%28n%29%20%5Cleq%20cg%28n%29%20%5Ctext%7B%20for%20all%20%7D%20n%20%5Cgeq%20n_0%5C%7D%0A
"
O(g(n)) = \\{f(n) : \\text{ there exist positive constants } c \\text{ and } n_0 \\text{ such that } \\\\
0 \\leq f(n) \\leq cg(n) \\text{ for all } n \\geq n_0\\}
")  

In words: for all values ![n](https://latex.codecogs.com/png.latex?n
"n") at and to the right of
![n\_0](https://latex.codecogs.com/png.latex?n_0 "n_0"), the value of
the function ![f(n)](https://latex.codecogs.com/png.latex?f%28n%29
"f(n)") is on or below
![cg(n)](https://latex.codecogs.com/png.latex?cg%28n%29 "cg(n)").

**Compare to ![\\Theta](https://latex.codecogs.com/png.latex?%5CTheta
"\\Theta")-notation**

  - ![\\Theta](https://latex.codecogs.com/png.latex?%5CTheta
    "\\Theta")-notation asymptotically bounds a function from above
    *and* below.
  - ![O](https://latex.codecogs.com/png.latex?O "O")-notation
    asymptotically bounds a function from *above only*.
  - ![\\Theta](https://latex.codecogs.com/png.latex?%5CTheta
    "\\Theta")-notation is stronger than
    ![O](https://latex.codecogs.com/png.latex?O "O")-notation, so
    ![O(g(n)) \\subset
    \\Theta(g(n))](https://latex.codecogs.com/png.latex?O%28g%28n%29%29%20%5Csubset%20%5CTheta%28g%28n%29%29
    "O(g(n)) \\subset \\Theta(g(n))").
  - ![O](https://latex.codecogs.com/png.latex?O "O")-notation makes no
    claims about how tight the bound is.

*When bounding running time*

  - When we use ![O](https://latex.codecogs.com/png.latex?O
    "O")-notation to bound the worst-case running time of an algorithm,
    we have a bound on the running-time on *every* input, because it is
    an **upper** bound.
  - In contrast, a
    ![\\Theta(n^2)](https://latex.codecogs.com/png.latex?%5CTheta%28n%5E2%29
    "\\Theta(n^2)") bound on the worst-case running time does **not**
    imply a
    ![\\Theta(n^2)](https://latex.codecogs.com/png.latex?%5CTheta%28n%5E2%29
    "\\Theta(n^2)") bound on the running time for all imputs.

**![o](https://latex.codecogs.com/png.latex?o "o")-notation**

  - Denotes an upper bound that is *not* asymptotically tight.

  
![
o(g(n)) = \\{f(n) : \\text{ for any positive constant } c \> 0 \\text{
there exists a constant } n\_0 \> 0 \\text{ such that } \\\\
0 \\leq f(n) \< cg(n) \\text{ for all } n \\geq n\_0\\}
](https://latex.codecogs.com/png.latex?%0Ao%28g%28n%29%29%20%3D%20%5C%7Bf%28n%29%20%3A%20%5Ctext%7B%20for%20any%20positive%20constant%20%7D%20c%20%3E%200%20%5Ctext%7B%20there%20exists%20a%20constant%20%7D%20n_0%20%3E%200%20%5Ctext%7B%20such%20that%20%7D%20%5C%5C%0A0%20%5Cleq%20f%28n%29%20%3C%20cg%28n%29%20%5Ctext%7B%20for%20all%20%7D%20n%20%5Cgeq%20n_0%5C%7D%0A
"
o(g(n)) = \\{f(n) : \\text{ for any positive constant } c \> 0 \\text{ there exists a constant } n_0 \> 0 \\text{ such that } \\\\
0 \\leq f(n) \< cg(n) \\text{ for all } n \\geq n_0\\}
")  

Intuitively, ![f(n)](https://latex.codecogs.com/png.latex?f%28n%29
"f(n)") becomes insignificant relative to
![g(n)](https://latex.codecogs.com/png.latex?g%28n%29 "g(n)") as ![n
\\to \\infty](https://latex.codecogs.com/png.latex?n%20%5Cto%20%5Cinfty
"n \\to \\infty") or   
![
\\lim\_{n \\to \\infty} \\frac{f(n)}{g(n)} = 0
](https://latex.codecogs.com/png.latex?%0A%5Clim_%7Bn%20%5Cto%20%5Cinfty%7D%20%5Cfrac%7Bf%28n%29%7D%7Bg%28n%29%7D%20%3D%200%0A
"
\\lim_{n \\to \\infty} \\frac{f(n)}{g(n)} = 0
")  

e.g. ![2n =
o(n^2)](https://latex.codecogs.com/png.latex?2n%20%3D%20o%28n%5E2%29
"2n = o(n^2)") but ![2n^2 \\neq
o(n^2)](https://latex.codecogs.com/png.latex?2n%5E2%20%5Cneq%20o%28n%5E2%29
"2n^2 \\neq o(n^2)")

#### ![\\Omega](https://latex.codecogs.com/png.latex?%5COmega "\\Omega")-notation

An asymptotic lower bound

**Definition**

  
![
\\Omega(g(n)) = \\{f(n) : \\text{ there exist positive constants } c
\\text{ and } n\_0 \\text{ such that } \\\\
0 \\leq cg(n) \\leq f(n) \\text{ for all } n \\geq n\_0\\}
](https://latex.codecogs.com/png.latex?%0A%5COmega%28g%28n%29%29%20%3D%20%5C%7Bf%28n%29%20%3A%20%5Ctext%7B%20there%20exist%20positive%20constants%20%7D%20c%20%5Ctext%7B%20and%20%7D%20n_0%20%5Ctext%7B%20such%20that%20%7D%20%5C%5C%0A0%20%5Cleq%20cg%28n%29%20%5Cleq%20f%28n%29%20%5Ctext%7B%20for%20all%20%7D%20n%20%5Cgeq%20n_0%5C%7D%0A
"
\\Omega(g(n)) = \\{f(n) : \\text{ there exist positive constants } c \\text{ and } n_0 \\text{ such that } \\\\
0 \\leq cg(n) \\leq f(n) \\text{ for all } n \\geq n_0\\}
")  

In words: for all values of ![n](https://latex.codecogs.com/png.latex?n
"n") at or to the right of
![n\_0](https://latex.codecogs.com/png.latex?n_0 "n_0"), the value of
![f(n)](https://latex.codecogs.com/png.latex?f%28n%29 "f(n)") is on or
above ![cg(n)](https://latex.codecogs.com/png.latex?cg%28n%29 "cg(n)").

**![\\omega](https://latex.codecogs.com/png.latex?%5Comega
"\\omega")-notation**

  - ![\\omega](https://latex.codecogs.com/png.latex?%5Comega
    "\\omega")-notation is to
    ![\\Omega](https://latex.codecogs.com/png.latex?%5COmega
    "\\Omega")-notation as ![o](https://latex.codecogs.com/png.latex?o
    "o")-notation is to ![O](https://latex.codecogs.com/png.latex?O
    "O")-notation

e.g. ![\\frac{n^2}{2} =
\\omega(n)](https://latex.codecogs.com/png.latex?%5Cfrac%7Bn%5E2%7D%7B2%7D%20%3D%20%5Comega%28n%29
"\\frac{n^2}{2} = \\omega(n)") but ![\\frac{n^2}{2} \\neq
\\omega(n^2)](https://latex.codecogs.com/png.latex?%5Cfrac%7Bn%5E2%7D%7B2%7D%20%5Cneq%20%5Comega%28n%5E2%29
"\\frac{n^2}{2} \\neq \\omega(n^2)").

#### Properties & Comparing Functions

**Theorem** For any two functions
![f(n)](https://latex.codecogs.com/png.latex?f%28n%29 "f(n)") and
![g(n)](https://latex.codecogs.com/png.latex?g%28n%29 "g(n)"), we have
![f(n) =
\\Theta(g(n))](https://latex.codecogs.com/png.latex?f%28n%29%20%3D%20%5CTheta%28g%28n%29%29
"f(n) = \\Theta(g(n))") if and only if ![f(n) =
O(g(n))](https://latex.codecogs.com/png.latex?f%28n%29%20%3D%20O%28g%28n%29%29
"f(n) = O(g(n))") and ![f(n) =
\\Omega(g(n))](https://latex.codecogs.com/png.latex?f%28n%29%20%3D%20%5COmega%28g%28n%29%29
"f(n) = \\Omega(g(n))").

**Transitivity**

Let ![X](https://latex.codecogs.com/png.latex?X "X") denote one of
![\\Theta, O, o, \\Omega,
\\omega](https://latex.codecogs.com/png.latex?%5CTheta%2C%20O%2C%20o%2C%20%5COmega%2C%20%5Comega
"\\Theta, O, o, \\Omega, \\omega").

  
![
f(n) = X(g(n)) \\text{ and } g(n) = X(h(n)) \\Rightarrow f(n) = X(h(n))
](https://latex.codecogs.com/png.latex?%0Af%28n%29%20%3D%20X%28g%28n%29%29%20%5Ctext%7B%20and%20%7D%20g%28n%29%20%3D%20X%28h%28n%29%29%20%5CRightarrow%20f%28n%29%20%3D%20X%28h%28n%29%29%0A
"
f(n) = X(g(n)) \\text{ and } g(n) = X(h(n)) \\Rightarrow f(n) = X(h(n))
")  

**Reflexivity**

Let ![Y](https://latex.codecogs.com/png.latex?Y "Y") denote one of
![\\Theta, O,
\\Omega](https://latex.codecogs.com/png.latex?%5CTheta%2C%20O%2C%20%5COmega
"\\Theta, O, \\Omega")

  
![
f(n) = Y(f(n))
](https://latex.codecogs.com/png.latex?%0Af%28n%29%20%3D%20Y%28f%28n%29%29%0A
"
f(n) = Y(f(n))
")  

**Symmetry**

  
![
f(n) = \\Theta(g(n)) \\text{ if and only if } g(n) = \\Theta(f(n))
](https://latex.codecogs.com/png.latex?%0Af%28n%29%20%3D%20%5CTheta%28g%28n%29%29%20%5Ctext%7B%20if%20and%20only%20if%20%7D%20g%28n%29%20%3D%20%5CTheta%28f%28n%29%29%0A
"
f(n) = \\Theta(g(n)) \\text{ if and only if } g(n) = \\Theta(f(n))
")  

**Transpose Symmetry**

  
![
f(n) = O(g(n)) \\text{ if and only if } g(n) = \\Omega(f(n))\\\\
f(n) = o(g(n)) \\text{ if and only if } g(n) = \\omega(f(n))
](https://latex.codecogs.com/png.latex?%0Af%28n%29%20%3D%20O%28g%28n%29%29%20%5Ctext%7B%20if%20and%20only%20if%20%7D%20g%28n%29%20%3D%20%5COmega%28f%28n%29%29%5C%5C%0Af%28n%29%20%3D%20o%28g%28n%29%29%20%5Ctext%7B%20if%20and%20only%20if%20%7D%20g%28n%29%20%3D%20%5Comega%28f%28n%29%29%0A
"
f(n) = O(g(n)) \\text{ if and only if } g(n) = \\Omega(f(n))\\\\
f(n) = o(g(n)) \\text{ if and only if } g(n) = \\omega(f(n))
")  
**Analogy to real numbers**

![f(n) =
O(g(n))](https://latex.codecogs.com/png.latex?f%28n%29%20%3D%20O%28g%28n%29%29
"f(n) = O(g(n))") is like ![a \\leq
b](https://latex.codecogs.com/png.latex?a%20%5Cleq%20b "a \\leq b")
![f(n) =
\\Omega(g(n))](https://latex.codecogs.com/png.latex?f%28n%29%20%3D%20%5COmega%28g%28n%29%29
"f(n) = \\Omega(g(n))") is like ![a \\geq
b](https://latex.codecogs.com/png.latex?a%20%5Cgeq%20b "a \\geq b")
![f(n) =
\\Theta(g(n))](https://latex.codecogs.com/png.latex?f%28n%29%20%3D%20%5CTheta%28g%28n%29%29
"f(n) = \\Theta(g(n))") is like ![a =
b](https://latex.codecogs.com/png.latex?a%20%3D%20b "a = b") ![f(n) =
o(g(n))](https://latex.codecogs.com/png.latex?f%28n%29%20%3D%20o%28g%28n%29%29
"f(n) = o(g(n))") is like ![a \<
b](https://latex.codecogs.com/png.latex?a%20%3C%20b "a \< b"),
“![f(n)](https://latex.codecogs.com/png.latex?f%28n%29 "f(n)") is
asymptotically smaller than
![g(n)](https://latex.codecogs.com/png.latex?g%28n%29 "g(n)")” ![f(n) =
\\omega(g(n))](https://latex.codecogs.com/png.latex?f%28n%29%20%3D%20%5Comega%28g%28n%29%29
"f(n) = \\omega(g(n))") is like ![a \>
b](https://latex.codecogs.com/png.latex?a%20%3E%20b "a \> b"),
“![f(n)](https://latex.codecogs.com/png.latex?f%28n%29 "f(n)") is
asymptotically larger than
![g(n)](https://latex.codecogs.com/png.latex?g%28n%29 "g(n)")”

*Note* that not all functions are asymptotically comparable (unlike real
numbers)

#### Common Complexities in this course

In increasing complexity:

![O(1) \< O(\\log N) \< O(N) \< O(N\\log N) \<
O(N^2)](https://latex.codecogs.com/png.latex?O%281%29%20%3C%20O%28%5Clog%20N%29%20%3C%20O%28N%29%20%3C%20O%28N%5Clog%20N%29%20%3C%20O%28N%5E2%29
"O(1) \< O(\\log N) \< O(N) \< O(N\\log N) \< O(N^2)")

*Note*: ![O](https://latex.codecogs.com/png.latex?O "O") usually used to
mean ![\\Theta](https://latex.codecogs.com/png.latex?%5CTheta
"\\Theta").

### Standard Notations and Common Functions

See Chapter 3.2 of the text for detailed definitions of standard
mathematical functions and notations and the relationships between them.

### Matrices

See Appendix D for basic matrix definitions and operations

### The Python Cost Model

See
[here](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-006-introduction-to-algorithms-fall-2011/readings/python-cost-model/)
for a full list of Python operations and their run times, with code to
execute runtime experiments.

### Peak Finding

#### One-Dimensional version

**Definition**: An element at position
![i](https://latex.codecogs.com/png.latex?i "i") in an array is a peak
if the elements in positions ![i
- 1](https://latex.codecogs.com/png.latex?i%20-%201 "i - 1") and ![i
+ 1](https://latex.codecogs.com/png.latex?i%20%2B%201 "i + 1") (or to
one side if on the edge) are less than or equal to the element at
position ![i](https://latex.codecogs.com/png.latex?i "i").

**Problem**: Find a peak if it exists. (Note we can show it always
exists)

**Straightforward Linear Algorithm**:

  - Start from one side and work to the other
  - Worst case you look at all the elements, so worst-case runtime is
    ![\\Theta(n)](https://latex.codecogs.com/png.latex?%5CTheta%28n%29
    "\\Theta(n)").

**Divide & Conquer**:

Start at position ![n/2](https://latex.codecogs.com/png.latex?n%2F2
"n/2"). If ![x\[n/2
- 1\]](https://latex.codecogs.com/png.latex?x%5Bn%2F2%20-%201%5D
"x[n/2 - 1]") \>
![x\[n/2\]](https://latex.codecogs.com/png.latex?x%5Bn%2F2%5D "x[n/2]"),
look at
![x\[0\]...x\[n/2-1\]](https://latex.codecogs.com/png.latex?x%5B0%5D...x%5Bn%2F2-1%5D
"x[0]...x[n/2-1]") for a peak. Else if ![x\[n/2
+ 1\]](https://latex.codecogs.com/png.latex?x%5Bn%2F2%20%2B%201%5D
"x[n/2 + 1]") \>
![x\[n/2\]](https://latex.codecogs.com/png.latex?x%5Bn%2F2%5D "x[n/2]"),
look at ![x\[n/2
+1\]...x\[n\]](https://latex.codecogs.com/png.latex?x%5Bn%2F2%20%2B1%5D...x%5Bn%5D
"x[n/2 +1]...x[n]") for a peak. Else, we are done and
![x\[n/2\]](https://latex.codecogs.com/png.latex?x%5Bn%2F2%5D "x[n/2]")
is a peak.

**Definition**: ![T(n)](https://latex.codecogs.com/png.latex?T%28n%29
"T(n)") = The “work” the algorithm does on input of size
![n](https://latex.codecogs.com/png.latex?n "n").

Then in this case ![T(n) = T(n/2) +
\\Theta(1)](https://latex.codecogs.com/png.latex?T%28n%29%20%3D%20T%28n%2F2%29%20%2B%20%5CTheta%281%29
"T(n) = T(n/2) + \\Theta(1)").

Base case: ![T(1) =
\\Theta(1)](https://latex.codecogs.com/png.latex?T%281%29%20%3D%20%5CTheta%281%29
"T(1) = \\Theta(1)")

So: ![T(n) = T(1) + ... +
T(1)](https://latex.codecogs.com/png.latex?T%28n%29%20%3D%20T%281%29%20%2B%20...%20%2B%20T%281%29
"T(n) = T(1) + ... + T(1)"), ![\\log\_2
n](https://latex.codecogs.com/png.latex?%5Clog_2%20n "\\log_2 n") times
= ![\\Theta(\\log\_2
n)](https://latex.codecogs.com/png.latex?%5CTheta%28%5Clog_2%20n%29
"\\Theta(\\log_2 n)")

#### Two-Dimensional Version

**Definition**: Let ![X](https://latex.codecogs.com/png.latex?X "X") be
an ![n x m](https://latex.codecogs.com/png.latex?n%20x%20m "n x m")
matrix. ![X\[i,j\]](https://latex.codecogs.com/png.latex?X%5Bi%2Cj%5D
"X[i,j]") is a peak if ![X\[i,j\] \\geq X\[i\\pm 1,
j\]](https://latex.codecogs.com/png.latex?X%5Bi%2Cj%5D%20%5Cgeq%20X%5Bi%5Cpm%201%2C%20j%5D
"X[i,j] \\geq X[i\\pm 1, j]") and ![X\[i,j\] \\geq X\[i, j
\\pm 1\]](https://latex.codecogs.com/png.latex?X%5Bi%2Cj%5D%20%5Cgeq%20X%5Bi%2C%20j%20%5Cpm%201%5D
"X[i,j] \\geq X[i, j \\pm 1]"). (Peak always exists)

**Greedy ascent algorithm**: \* Pick a direction and try to follow it to
find a peak. Keep going while you are increasing. \*
![\\Theta(nm)](https://latex.codecogs.com/png.latex?%5CTheta%28nm%29
"\\Theta(nm)") complexity.

**Divide & Conqueer**: \* Pick a middle column ![j =
m/2](https://latex.codecogs.com/png.latex?j%20%3D%20m%2F2 "j = m/2") \*
Find the global maximum of that column at
![(i,j)](https://latex.codecogs.com/png.latex?%28i%2Cj%29 "(i,j)") \* If
![(i, j-1) \> (i,
j)](https://latex.codecogs.com/png.latex?%28i%2C%20j-1%29%20%3E%20%28i%2C%20j%29
"(i, j-1) \> (i, j)"), look at columns
0,…,![j-1](https://latex.codecogs.com/png.latex?j-1 "j-1") for a peak.
\* Else if ![i, j+1) \>
(i,j)](https://latex.codecogs.com/png.latex?i%2C%20j%2B1%29%20%3E%20%28i%2Cj%29
"i, j+1) \> (i,j)"), look at columns
![j+1](https://latex.codecogs.com/png.latex?j%2B1
"j+1"),…,![m](https://latex.codecogs.com/png.latex?m "m") for a peak.
\* Else ![(i,j)](https://latex.codecogs.com/png.latex?%28i%2Cj%29
"(i,j)") is a 2-D peak. \* When you have a single column, the global max
in the column is a peak.

Then ![T(n, m) = T(n, m/2) +
\\Theta(n)](https://latex.codecogs.com/png.latex?T%28n%2C%20m%29%20%3D%20T%28n%2C%20m%2F2%29%20%2B%20%5CTheta%28n%29
"T(n, m) = T(n, m/2) + \\Theta(n)") (since finding a global max is
![\\Theta(n)](https://latex.codecogs.com/png.latex?%5CTheta%28n%29
"\\Theta(n)"))

Base case: ![T(n, 1) =
\\Theta(n)](https://latex.codecogs.com/png.latex?T%28n%2C%201%29%20%3D%20%5CTheta%28n%29
"T(n, 1) = \\Theta(n)")

So: ![T(n, m) = \\Theta(n) + ... +
\\Theta(n)](https://latex.codecogs.com/png.latex?T%28n%2C%20m%29%20%3D%20%5CTheta%28n%29%20%2B%20...%20%2B%20%5CTheta%28n%29
"T(n, m) = \\Theta(n) + ... + \\Theta(n)") ![\\log\_2
m](https://latex.codecogs.com/png.latex?%5Clog_2%20m "\\log_2 m") times
![= \\Theta(n\\log\_2
m)](https://latex.codecogs.com/png.latex?%3D%20%5CTheta%28n%5Clog_2%20m%29
"= \\Theta(n\\log_2 m)")

## Unit 2: Sorting and Trees

### Insertion Sort

  - Efficient for small input
  - ![O(n^2)](https://latex.codecogs.com/png.latex?O%28n%5E2%29
    "O(n^2)")
  - Similar to how humans sort cards: start with all cards in right
    hand. One by one, place cards in sorted order in left hand, working
    from right to left to find correct position.

**PSEUDOCODE**

``` python
for j = 2 to A.length:
  key = A[j]
  # insert A[j] into the sorted sequence A[1...j-1]
  i = j - 1
  while i > 0 and A[i] > key:
    A[i + 1] = A[i]
    i = i - 1
  A[i + 1] = key
```
