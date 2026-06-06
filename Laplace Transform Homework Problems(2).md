Laplace Transform Homework Problems(2)

Problem

Solve the initial value problem using the Laplace Transform:
$2\frac{d ^2x}{dt^2}+7\frac{dx}{dt}+3x=0$

with initial conditions
x(0)=0,x′(0)=1

Step 1: Take the Laplace Transform

Let
L{x(t)}=X(s)

Using the Laplace transform formulas:

L{x''(t)}=s²X(s)-sX(0)-x'(0)

L{x'(t)} = sX(s) - x(0)

aking the Laplace transform of both sides of the differential equation:

$2[s^2X(s)-sx(0)-x'(0)]+7[sX(s)-x(0)]+3X(s)=0$

Substituting the initial conditions
$x(0)=0,x′(0)=1$

gives

$2(s^2X(s)−1)+7sX(s)+3X(s)=0$

Simplifying:

$(2s^2+7s+3)X(s)=2$

Therefore,

$X(s)=\frac{2}{2s^2+7s+3}$

Step 2: Partial Fraction Decomposition

Factor the denominator:
$2s^2+7s+3=(2s+1)(s+3)$

Thus,

$X(s)=\frac{2}{(2s+1)(s+3)}$

Assume

$\frac{2}{(2s+1)(s+3)}=\frac{A}{2s+1}+\frac{B}{s+3}$

Multiplying both sides by (2s+1)(s+3):

$2=A(s+3)+B(2s+1)$

Comparing coefficients
A+2B=0
3A+B=2

Solving gives

$A=\frac{4}{5},   B=-\frac{2}{5}$

Hence,

$X(s)=\frac{4}{5(2s+1)}-\frac{2}{5(s+3)}$

Since

$\frac{4}{5(2s+1)}=\frac{2}{5}\cdot\frac{1}{s+\frac{1}{2}}$

we obtain

$X(s)=\frac{2}{5}\frac{1}{s+\frac{1}{2}}-\frac{2}{5}\frac{1}{s+3}$

Step 3: Apply the Inverse Laplace Transform

Using

$\mathcal{L}^{-1}\{\frac{1}{s+a}\}=e^{-at}$

we get

$x(t)=\frac{5}{2}e^{-t/2}-\frac{5}{2}e^{-3t}$

Final Answer

$x(t)=\frac{2}{5}(e^{-t/2}-e^{-3t})$
