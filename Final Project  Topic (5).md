Final Project  Topic (5)

Given

An RC low-pass filter is commonly used in signal acquisition circuits to remove high-frequency noise. The filter parameters are

R=1kΩ=1000Ω

$C=1\,\mu F=10^{-6}\,F$

Therefore,

$RC=1000\times10^{-6}=10^{-3}\ \text{s}$

The input signal is

$f(t)=\left[\sin(10t)+0.5\sin(1000t)\right]u(t)$

where

- $\sin(10t)$ is the desired low-frequency signal.
  
- $0.5\sin(1000t)$ is the high-frequency noise.
  
- $u(t)$ is the unit step function.

The capacitor is initially uncharged, so the initial condition is

y(0)=0.

Use the **Laplace transform** to determine the output voltage y(t) and verify the filtering effect of the RC low-pass filter on the high-frequency noise.

# Step 1. Establish the Differential Equation

The governing equation of an RC low-pass filter is

$RC\frac{dy(t)}{dt}+y(t)=f(t).$

Substituting

$RC=10^{-3},$

gives

$10^{-3}\frac{dy(t)}{dt}+y(t)=\sin(10t)+0.5\sin(1000t).$

# Step 2. Apply the Laplace Transform

Using

$\mathcal{L}\{\frac{dy}{dt}\}=sY(s)-y(0),$

and since

y(0)=0,

we obtain

$10^{-3}sY(s)+Y(s)=\frac{10}{s^2+100}+0.5\left(\frac{1000}{s^2+1000000}\right).$

Thus,

$Y(s)=\frac{\frac{10}{s^2+100}+\frac{500}{s^2+1000000}}{0.001s+1}.$

Since

$0.001s+1=\frac{s+1000}{1000},$

we have

$Y(s)=1000\left(\frac{10}{(s^2+100)(s+1000)}+\frac{500}{(s^2+1000000)(s+1000)}\right).$

Therefore,

$Y(s)=\frac{10000}{(s^2+100)(s+1000)}+\frac{500000}{(s^2+1000000)(s+1000)}.$

# Step 3. Partial Fraction Expansion of the First Term

Assume

$\frac{10000}{(s+1000)(s^2+100)}=\frac{A}{s+1000}+\frac{Bs+C}{s^2+100}.$

By comparing coefficients,

$A=\frac{100}{10001},$

$B=-\frac{100}{10001},$

$C=\frac{100000}{10001}.$

Hence,

$Y_1(s)=\frac{100/10001}{s+1000}-\frac{100}{10001}\frac{s}{s^2+100}+\frac{100000}{10001}\frac1{s^2+100}.$

Inverse Laplace Transform

Using

$\mathcal{L}^{-1}\({\frac1{s+a}\})=e^{-at},$

$\mathcal{L}^{-1}\({\frac{s}{s^2+\omega^2}\})=\cos(\omega t),$

$\mathcal{L}^{-1}\({\frac{\omega}{s^2+\omega^2}\})=\sin(\omega t),$

we obtain

$y_1(t)=\frac{100}{10001}e^{-1000t}-\frac{100}{10001}\cos(10t)+\frac{10000}{10001}\sin(10t).$

# Step 4. Partial Fraction Expansion of the Second Term

Assume

$\frac{500000}{(s+1000)(s^2+1000000)}=\frac{D}{s+1000}+\frac{Es+F}{s^2+1000000}.$

Comparing coefficients gives

$D=\frac14,$

$E=-\frac14,$

F=250.

Therefore,

$Y_2(s)=\frac{1}{4(s+1000)}-\frac14\frac{s}{s^2+1000000}+250\frac1{s^2+1000000}.$

Inverse Laplace Transform

Since

$250\frac1{s^2+1000000}=\frac14\frac{1000}{s^2+1000000},$

we obtain

$y_2(t)=\frac14e^{-1000t}-\frac14\cos(1000t)+\frac14\sin(1000t).$

# Step 5. Obtain the Output Voltage

Combining the two parts,

$$
\boxed{
\begin{aligned}
y(t)=&
\left(
\frac{100}{10001}
+\frac14
\right)e^{-1000t}
\\
&
-\frac{100}{10001}\cos(10t)
+\frac{10000}{10001}\sin(10t)
\\
&
-\frac14\cos(1000t)
+\frac14\sin(1000t).
\end{aligned}
}
$$

# Step 6. Steady-State Response

As

$t\rightarrow\infty,$

the exponential term vanishes,

$e^{-1000t}\rightarrow0.$

Therefore, the steady-state output is

$\boxed{y_{ss}(t)=-\frac{100}{10001}\cos(10t)+\frac{10000}{10001}\sin(10t)-\frac14\cos(1000t)+\frac14\sin(1000t).}$

# Step 7. Verification of the Low-Pass Filtering Effect

The transfer function of the RC low-pass filter is

$H(s)=\frac1{RCs+1}.$

Its frequency response is

$|H(j\omega)|=\frac1{\sqrt{1+(\omega RC)^2}}.$

### (1) Low-Frequency Signal

For

$\omega=10,$

the magnitude response is

$|H(j10)|=\frac1{\sqrt{1+(10\times0.001)^2}}=0.99995\approx1.$

Thus, the low-frequency signal passes through the filter almost without attenuation.

### (2) High-Frequency Noise

For

$\omega=1000,$

the magnitude response is

$|H(j1000)|=\frac1{\sqrt2}=0.707.$

The original noise amplitude is

0.5.

After filtering, the output amplitude becomes

$0.5\times0.707=0.354.$

Therefore, the high-frequency noise is significantly attenuated.

# Conclusion

1. Using the Laplace transform, the output voltage of the RC low-pass filter is

$$
\boxed{
\begin{aligned}
y(t)=&
\left(
\frac{100}{10001}
+\frac14
\right)e^{-1000t}
\\
&
-\frac{100}{10001}\cos(10t)
+\frac{10000}{10001}\sin(10t)
\\
&
-\frac14\cos(1000t)
+\frac14\sin(1000t).
\end{aligned}
}
$$

2. The transient term $e^{-1000t}$ decays rapidly to zero.

3. The desired low-frequency signal $\sin(10t)$ is preserved almost completely, while the amplitude of the high-frequency noise $\sin(1000t)$ is reduced from 0.5 to approximately 0.354. This verifies that the RC low-pass filter effectively suppresses high-frequency noise while retaining the desired low-frequency signal.
