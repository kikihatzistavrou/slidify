---
title       : R Programming
subtitle    : Solving a Quadratic Equation 
author      : Kiki Hatzistavrou
job         : Student
framework   : io2012 # {io2012, html5slides, shower, dzslides,revealjs ...}

highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax]     # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
---

## Introduction

> 1. A quadratic equation is any equation having the form: $$ax^2+bx+c=0$$
where $x$ represents an unknown, and $a$, $b$, and $c$ represent known numbers such that $a \neq 0$. 
> 2. If $a = 0$, then the equation is linear, not quadratic. 
> 3. The numbers $a$, $b$, and $c$ are the coefficients of the equation, and may be distinguished by calling them, respectively, the quadratic coefficient, the linear coefficient and the constant or free term.

--- .class #id 

## Solving the equation

In the quadratic formula, the expression underneath the square root sign is called the discriminant of the quadratic equation :
$$\Delta = b^2 - 4ac$$

> 1. If the discriminant is positive, then there are two distinct roots, both of which are real numbers :
$$x_{1,2} =\frac{-b \pm \sqrt {\Delta}}{2a}.$$

> 2. If the discriminant is zero, then there is exactly one real root that sometimes is called double root : $$x = -\frac{b}{2a}.$$

> 3. If the discriminant is negative, then there are no real roots.

--- .class #id 

## Creating the function


```r
# Constructing Quadratic Formula
result <- function(a,b,c){
  if(delta(a,b,c) > 0){ # first case D>0
        x_1 = (-b+sqrt(delta(a,b,c)))/(2*a)
        x_2 = (-b-sqrt(delta(a,b,c)))/(2*a)
        result = c(x_1,x_2)
  }
  else if(delta(a,b,c) == 0){ # second case D=0
        x = -b/(2*a)
  }
  else {"There are no real roots."} # third case D<0
}

# Constructing delta
delta<-function(a,b,c){
      b^2-4*a*c
}
```

--- .class #id 

## Examples

a) $\quad$ $x^2-2x+1=0$  $\quad$  $\quad$    b) $\quad$ $x^2-4x+3=0$   $\quad$  $\quad$     c) $\quad$ $4x^2-x+5=0$ 

```r
a <- result(1,-2,1); a
```

```
## [1] 1
```

```r
b <- result(1,-4,1); b
```

```
## [1] 3.7320508 0.2679492
```

```r
c <- result(4,-1,5); c
```

```
## [1] "There are no real roots."
```






