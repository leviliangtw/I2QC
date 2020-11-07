# Sheet 01

## Exercise 1.1

### \(a\)

$$
\begin{split}
|\psi\rangle &= 
\mathrm{e}^{i\gamma}(\cos\frac{\theta}{2}|0\rangle + \mathrm{e}^{i\psi}\sin\frac{\theta}{2}|1\rangle)\\&= 
\frac{i}{2}|0\rangle - \frac{\sqrt{3}}{2}|1\rangle = 
\mathrm{e}^{i\frac{\pi}{2}}\cos\frac{\pi}{3}|0\rangle - \sin\frac{\pi}{3}|1\rangle = 
\mathrm{e}^{i\frac{\pi}{2}}(\cos\frac{\pi}{3}|0\rangle - \mathrm{e}^{-i\frac{\pi}{2}}\sin\frac{\pi}{3}|1\rangle)\\&= 
\mathrm{e}^{i\frac{\pi}{2}}(\cos\frac{\pi}{3}|0\rangle + \mathrm{e}^{i\frac{\pi}{2}}\sin\frac{\pi}{3}|1\rangle)
\end{split}
$$

Therefore

$$
\theta = \dfrac{\pi}{3},\ \psi = \dfrac{\pi}{2},\ 
\vec{\gamma} = 
\begin{pmatrix}
\dfrac{\sqrt{6}}{4} & \dfrac{\sqrt{2}}{4} & \dfrac{1}{2}
\end{pmatrix}
$$

### \(b\)

$$
\begin{split}
R_x(\frac{2\pi}{3})|\psi\rangle &= 
\begin{pmatrix}
\cos\frac{\pi}{3} & -i\sin\frac{\pi}{3}
\\
-i\sin\frac{\pi}{3} & \cos\frac{\pi}{3}
\end{pmatrix}
\begin{pmatrix}
\cos\frac{\pi}{3} 
\\
\mathrm{e}^{i\frac{\pi}{2}}\sin\frac{\pi}{3}
\end{pmatrix} = 
\begin{pmatrix}
\cos\frac{\pi}{3} & -i\sin\frac{\pi}{3}
\\
-i\sin\frac{\pi}{3} & \cos\frac{\pi}{3}
\end{pmatrix}
\begin{pmatrix}
\cos\frac{\pi}{3} 
\\
i\sin\frac{\pi}{3}
\end{pmatrix} \\&=
\begin{pmatrix}
\cos^2\frac{\pi}{3}  + \sin^2\frac{\pi}{3}
\\
-i\sin\frac{\pi}{3}\cos\frac{\pi}{3} + i\sin\frac{\pi}{3}\cos\frac{\pi}{3}
\end{pmatrix} = 
\begin{pmatrix}
1
\\
0
\end{pmatrix} = 
|0\rangle
\end{split}
$$

The operation $$R_x(\frac{2\pi}{3})$$ means rotate the state $$|\psi\rangle$$ around X-axis for $$\dfrac{2\pi}{3}$$ based on the right-hand rule.

### \(c\)

$$
\begin{split}
H &= \dfrac{1}{\sqrt{2}}
\begin{pmatrix}
1 & 1 \\
1 & -1
\end{pmatrix}
= 
\mathrm{e}^{i\frac{3\pi}{2}}
\begin{pmatrix}
\frac{i}{\sqrt{2}} & \frac{i}{\sqrt{2}} \\
\frac{i}{\sqrt{2}} & \frac{-i}{\sqrt{2}}
\end{pmatrix}
= 
\mathrm{e}^{i\frac{3\pi}{2}}
\begin{pmatrix}
-1 & 0 \\
0 & -1
\end{pmatrix}
\begin{pmatrix}
\frac{-i}{\sqrt{2}} & \frac{-i}{\sqrt{2}} \\
\frac{-i}{\sqrt{2}} & \frac{i}{\sqrt{2}}
\end{pmatrix}
\\&= 
\mathrm{e}^{i\frac{3\pi}{2}}
\begin{pmatrix}
-1 & 0 \\
0 & -1
\end{pmatrix}
\begin{pmatrix}
\frac{1}{\sqrt{2}} & \frac{-1}{\sqrt{2}} \\
\frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}}
\end{pmatrix}
\begin{pmatrix}
-i & 0 \\
0 & i
\end{pmatrix}
\\&=
\mathrm{e}^{i\frac{3\pi}{2}}
\begin{pmatrix}
\mathrm{e}^{-i(\frac{2\pi}{2})} & 0 \\
0 & \mathrm{e}^{i(\frac{2\pi}{2})}
\end{pmatrix}
\begin{pmatrix}
\cos\frac{(\pi/2)}{2} & -\sin\frac{(\pi/2)}{2} \\
\sin\frac{(\pi/2)}{2} & \cos\frac{(\pi/2)}{2}
\end{pmatrix}
\begin{pmatrix}
\mathrm{e}^{-i(\frac{\pi}{2})} & 0 \\
0 & \mathrm{e}^{i(\frac{\pi}{2})}
\end{pmatrix}
\\&=
\mathrm{e}^{i\frac{3\pi}{2}}R_z(2\pi)R_y(\frac{\pi}{2})R_z(\pi)
\end{split}
$$

## Exercise 1.2

### \(a\)

$$
Y \otimes Z = 
\begin{pmatrix}
0 & -i \\
i & 0
\end{pmatrix}
\otimes
\begin{pmatrix}
1 & 0 \\
0 & -1
\end{pmatrix}
=
\begin{pmatrix}
0 & 0 & -i & 0 \\
0 & 0 & 0 & i \\
i & 0 & 0 & 0 \\
0 & -i & 0 & 0 
\end{pmatrix}
$$

### \(B\)

![](.gitbook/assets/image%20%283%29.png)

### \(c\)

$$
\begin{split}
(Y \otimes Z) (|v\rangle \otimes |w\rangle) 
&= 
\begin{pmatrix}
0 & 0 & -i & 0 \\
0 & 0 & 0 & i \\
i & 0 & 0 & 0 \\
0 & -i & 0 & 0 
\end{pmatrix}
\begin{pmatrix}
3/5 \\
4/5
\end{pmatrix}
\otimes
\begin{pmatrix}
0 \\
1
\end{pmatrix}
=
\begin{pmatrix}
0 & 0 & -i & 0 \\
0 & 0 & 0 & i \\
i & 0 & 0 & 0 \\
0 & -i & 0 & 0 
\end{pmatrix}
\begin{pmatrix}
0 \\
3/5 \\
0 \\
4/5
\end{pmatrix}
\\&=
\begin{pmatrix}
0 \\
4i/5 \\
0 \\
-3i/5
\end{pmatrix}
\\
(Y |v\rangle) \otimes (Z |w\rangle) &=
\bigg [
 \begin{pmatrix}
0 & -i \\
i & 0 \\
\end{pmatrix}
 \begin{pmatrix}
3/5 \\
4/5 \\
\end{pmatrix}
\bigg ]
\otimes
\bigg [
\begin{pmatrix}
1 & 0 \\
0 & -1 \\
\end{pmatrix}
 \begin{pmatrix}
0 \\
1 \\
\end{pmatrix}
\bigg ]
=
 \begin{pmatrix}
-4i/5 \\
3i/5 \\
\end{pmatrix}
\otimes
 \begin{pmatrix}
0 \\
-1 \\
\end{pmatrix}
\\&=
\begin{pmatrix}
0 \\
4i/5 \\
0 \\
-3i/5
\end{pmatrix}
\end{split}
$$

Therefore

$$
(Y \otimes Z) (|v\rangle \otimes |w\rangle) 
= 
\begin{pmatrix}
0 \\
4i/5 \\
0 \\
-3i/5
\end{pmatrix}
= (Y |v\rangle) \otimes (Z |w\rangle)
$$

### \(d\)

Assume that

$$
\begin{split}
&|v\rangle = 
\begin{pmatrix}
v_1 \\
v_2
\end{pmatrix}
,\ 
|w\rangle = 
\begin{pmatrix}
w_1 \\
w_2
\end{pmatrix}
,\ 
v_1, v_2, w_1, w_2 \in \mathbb{C}
\\
\Rightarrow
&|v\rangle \otimes |w\rangle = 
\begin{pmatrix}
v_1w_1 \\
v_1w_2 \\
v_2w_1 \\
v_2w_2
\end{pmatrix}
=
|\psi\rangle 
=
\begin{pmatrix}
\frac{1}{\sqrt{2}} \\
0 \\
0 \\
\frac{1}{\sqrt{2}}
\end{pmatrix}
\end{split}
$$

$$
\begin{split}
&\begin{cases}
v_1w_1=\frac{1}{\sqrt{2}} \\
v_2w_2=\frac{1}{\sqrt{2}} \\
\end{cases}
\Rightarrow
v_1, v_2, w_1, w_2 \ne 0
\\
\\
&\begin{cases}
v_1w_2=0 \\
v_2w_1=0 \\
\end{cases}
\rightarrow \leftarrow
\end{split}
$$

Therefore

$$
|\psi\rangle 
\ne
|v\rangle \otimes |w\rangle
$$

