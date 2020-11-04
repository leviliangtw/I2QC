# 2. Introduction to quantum mechanics

概述量子運算的機制，理解上需要相當程度的線性代數基礎。

## 2.1. Quantum bits \(qubits\)

一個量子位元的表示法如下：

$$
|\psi\rangle=\alpha|0\rangle+\beta|1\rangle,\ \mathrm{with}\ \alpha,\beta\in\mathbb{C}\ \mathrm{and}\ |\alpha|^2+|\beta|^2=1 \ \mathrm{(normalization)}
\tag{2.1}
$$

$$
|0\rangle=\begin{pmatrix}{} 1 \\ 0 \end{pmatrix},\ |1\rangle=\begin{pmatrix}{} 0 \\ 1 \end{pmatrix}\to|\psi\rangle=\begin{pmatrix}{} \alpha \\ \beta \end{pmatrix}
\tag{2.2},\ \mathrm{and}\ |\psi\rangle\in\mathbb{C}^2
$$

複數的表示法為 $$a+bi$$ ，因此如果要定義$$\alpha$$ 與 $$\beta$$ ，照理而言需要4個變數。  
但為滿足 $$|\alpha|^2+|\beta|^2=1$$，且根據 $$\mathrm{Euler's\  Formula:e}^{i\psi}=\cos\psi+i\sin\psi$$ ，所以我們將$$\alpha$$ 與 $$\beta$$ 分別乘以$$\cos\dfrac{\theta}{2}$$ 與 $$\sin\dfrac{\theta}{2}$$ ，將變數減少為 $$3$$ 個，並定義如下：

$$
\alpha=\mathrm{e}^{i\gamma}\cos\dfrac{\theta}{2},\ 
\beta=\mathrm{e}^{i(\gamma+\psi)}\sin\dfrac{\theta}{2}
$$

![Source: https://commons.wikimedia.org/wiki/File:Euler%27s\_formula.png](.gitbook/assets/image.png)

接下來，我們來看看 $$|\psi\rangle$$ 是怎麼表示的：

$$
|\psi\rangle
=
\mathrm{e}^{i\gamma}\cos\dfrac{\theta}{2}|0\rangle
+
\mathrm{e}^{i(\gamma+\psi)}\cos\dfrac{\theta}{2}|1\rangle
=
\mathrm{e}^{i\gamma}(\cos\dfrac{\theta}{2}|0\rangle+\mathrm{e}^{i\psi}\sin\dfrac{\theta}{2}|1\rangle)
\tag{2.6}
$$

我們可以發現， $$|\psi\rangle$$ 內部產生了一個共同的因子 $$\mathrm{e}^{i\gamma}$$ ，稱為 $$\mathrm{overall\ (global)\ phase\ factor}$$ 。  
以物理角度而言，這種 $$\mathrm{global\ phase\ factor}$$ 是沒有意義的，只有相對的 $$\mathrm{phase\ factor}$$ ，意即 $$\mathrm{relative\ phase\ factor}$$，才有具意義。

![Source: https://commons.wikimedia.org/wiki/File:Bloch sphere.svg](.gitbook/assets/image%20%281%29.png)

如果就 $$\mathrm{Bloch\ Sphere}$$ 來解釋，$$|\psi\rangle$$ 即為此球面之向量空間。而 $$\mathrm{e}^{i\gamma}$$ 並不影響$$|\psi\rangle$$在此球面上的分布，故以此觀點來看， $$\mathrm{e}^{i\gamma}$$ 便可以忽略不計如下：  
\(思考： $$X軸$$ 與 $$Y軸$$ 組成的複數平面，加上$$|0\rangle$$與$$|1\rangle$$代表的 $$Z軸$$ ，最後形成 $$\mathrm{Bloch\ Sphere}$$。\)

$$
|\psi\rangle
=
\cos\dfrac{\theta}{2}|0\rangle+\mathrm{e}^{i\psi}\sin\dfrac{\theta}{2}|1\rangle
$$

如此一來，一個量子位元可以由 $$2$$ 個實數 $$\theta$$ 與 $$\psi$$ 表示。  
另外，以球面座標而言，$$|\psi\rangle$$ 也可描述為：

$$
\vec{r} = \begin{pmatrix} \cos(\psi)\sin(\phi) & \sin(\psi)\sin(\phi) & \cos(\phi) \end{pmatrix}
\tag{2.7}
$$

## 2.2. Single qubit gates

時間演變定理 $$\mathrm{(Principle\ of}\ time\ evolution\mathrm{)}$$ ：在時間點 $$t$$ 的量子態 $$\mathrm{(Quantum\ State)}$$ 為 $$|\psi\rangle$$ ，而在時間點 $$t^{\prime}>t$$ 時，此時量子態 $$|\psi\rangle^{\prime}$$ 的轉移矩陣可使用么正矩陣 $$\mathrm{(Unitary\ Matrix)}$$$$U$$ 表示：  
\(思考：**么正矩陣**的特性包含**保長度**及**保內積**，這為什麼對量子位元的**向量空間**重要？\)

$$
|\psi\rangle^{\prime}=U |\psi\rangle,
\\
\mathrm{and}\ 
\|U|\psi\rangle\| = \||\psi\rangle\| \ \mathrm{for\ all\ |\psi\rangle\in\mathbb{C}^2}
\tag{2.8}
$$

因此，

$$
|\psi\rangle = 
\begin{pmatrix} 
\alpha \\ 
\beta 
\end{pmatrix}
,\ 
|\psi\rangle^{\prime} = 
\begin{pmatrix} 
\alpha^{\prime} \\ 
\beta^{\prime} 
\end{pmatrix}
,\ 
U = 
\begin{pmatrix} 
a & b \\ 
c & d
\end{pmatrix}
,\ 
\tag{2.9}
$$

$$
|\psi\rangle^{\prime} = U |\psi\rangle
= 
\begin{pmatrix} 
a & b \\ 
c & d
\end{pmatrix}
\begin{pmatrix} 
\alpha^{\prime} \\ 
\beta^{\prime} 
\end{pmatrix}
=
\begin{pmatrix} 
a\alpha^{\prime} & b\beta^{\prime} \\ 
c\alpha^{\prime} & d\beta^{\prime}
\end{pmatrix}
\tag{2.10}
$$

接下來介紹三種基礎的量子閘 $$\mathrm{(Gate)}$$ ：  
\(視覺化模型可參考：[https://javafxpert.github.io/grok-bloch/](https://javafxpert.github.io/grok-bloch/)\)

* $$\mathrm{Pauli\ X\ gate}\ (\sigma_1)$$ ：如同傳統的 $$\mathrm{Not\ gate}$$ ，將 $$|0\rangle \leftrightarrow |1\rangle$$ 的係數反轉。 \(思考：當$$|1\rangle$$的係數是複數時，為了提出$$\mathrm{global\ phase\ factor}$$，該如何對 $$|\psi\rangle$$ 進行操作？\)

$$
X= \sigma_1 = 
\begin{pmatrix} 
0 & 1 \\ 
1 & 0 \\
\end{pmatrix}
\tag{2.11}
$$

* $$\mathrm{Pauli\ Y\ gate}\ (\sigma_2)$$ ：先將 $$|0\rangle \leftrightarrow |1\rangle$$ 的係數反轉，再分別乘以 $$i$$ 與 $$-i$$ 以進行座標的旋轉。 \(思考：$$\mathrm{e}^{i\frac{\pi}{2}} = i$$及$$\mathrm{e}^{i\frac{3\pi}{2}} = -i$$，反轉與旋轉後，該如何對 $$|\psi\rangle$$ 進行操作？\)

$$
Y= \sigma_1 = 
\begin{pmatrix} 
0 & -i \\ 
i  & 0 \\
\end{pmatrix}
\tag{2.12}
$$

* $$\mathrm{Pauli\ Z\ gate}\ (\sigma_3)$$ ：令 $$|0\rangle$$ 維持不變，翻轉 $$|1\rangle$$ 。

$$
Z= \sigma_1 = 
\begin{pmatrix} 
1 & 0 \\ 
0 & -1 \\
\end{pmatrix}
\tag{2.13}
$$

這裡來思考$$\sigma_3$$的運算，首先 $$|\psi\rangle = \cos\dfrac{\theta}{2}|0\rangle+\mathrm{e}^{i\psi}\sin\dfrac{\theta}{2}|1\rangle$$ ，因此我們以 $$\mathrm{e}^{i\pi} = -1$$ 進行反轉運算。

$$
Z|\psi\rangle = \cos\dfrac{\theta}{2}|0\rangle - \mathrm{e}^{i\psi}\sin\dfrac{\theta}{2}|1\rangle = \cos\dfrac{\theta}{2}|0\rangle + \mathrm{e}^{i(\psi+\pi)}\sin\dfrac{\theta}{2}|1\rangle 
\tag{2.15}
$$

在 $$\mathrm{Bloch\ Sphere}$$ 上觀察，即是繞著 $$Z軸$$ 旋轉 $$180\degree$$的結果。

而 $$X,\ Y,\ Z\ \mathrm{gates}$$ 稱作 $$\mathrm{Pauli\ Matrices}$$ 。  
向量表示： $$\mathrm{Pauli\ vector}\ \vec{\sigma} =  \begin{pmatrix}  \sigma_1 & \sigma_2 & \sigma_3 \\  \end{pmatrix} \ \mathrm{is\ a\ vector\ of\ 2 \times 2\ matrices}$$。

再來三種量子閘 $$\mathrm{(Gate)}$$ ：

* $$\mathrm{Hadamard\ gate}$$ ：

$$
H = \dfrac{1}{\sqrt{2}}
\begin{pmatrix}
1 & 1 \\
1 & -1 \\
\end{pmatrix}
\tag{2.16}
$$

* $$\mathrm{Phase\ gate}$$ ：沿著 $$Z軸$$ 轉 $$90\degree$$。

$$
S = 
\begin{pmatrix}
1 & 0 \\
0 & i \\
\end{pmatrix}
=
\begin{pmatrix}
1 & 0 \\
0 & \mathrm{e}^{i\frac{\pi}{2}}
\end{pmatrix}
\tag{2.17}
$$

* $$\mathrm{T\ gate}$$ ：沿著 $$Z軸$$ 轉 $$45\degree$$。

$$
T = 
\begin{pmatrix}
1 & 0 \\
0 & \mathrm{e}^{i\frac{\pi}{4}}
\end{pmatrix}
\tag{2.18}
$$

