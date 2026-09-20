$$
\sigma\in\left(0,+\infty\right)\:\:\:\delta\:\:\delta\:\hat\lbrace\delta\:\rbrace\:\:\:X_{1\:\:\:\:}X_{2\:\:}\:\:\:X_{n\:}\:E\left(\right)
$$

$$
=\dfrac{1}{n}\Sigma_{i=1}^{\infty}\left|X_{i}\right|\:\:E\left|X\right|=2\int_{0}^{\infty}\dfrac{1}{2\sigma}x\cdot e^{-\dfrac{x}{\sigma}}dx=\dfrac{1}{\sigma}\cdot\dfrac{1}{\left(\dfrac{1}{\sigma}\right)^{2}}=\sigma
$$

$$
E\left(X^{2}\right)=2\int_{0}^{\infty}\dfrac{1}{2\sigma}x^{2}\cdot e^{-\dfrac{x}{\sigma}}dx=\dfrac{1}{\sigma}\cdot\dfrac{2}{\left(\dfrac{1}{\sigma}\right)^{3}}=2\sigma^{2}
$$

$$
D\left(\left|X\right|\right)=E\left(X^{2}\right)-\left(E\left(X\right)\right)^{2}=\sigma^{2}
$$

$$
D\left(\right)=\dfrac{D\left(\left|X\right|\right)}{n}=\dfrac{\sigma^{2}}{n}
$$

$$
F\left(x;\theta\right)=1-e^{-\dfrac{x^{2}}{\theta}}\:\:\:x\geqslant0
$$

$$
F\left(x;\theta\right)=\left\{\begin{matrix}1-e^{-\dfrac{x^{2}}{\theta}}\:\:\:x\geqslant0\\ \\ 0\:\:\:\:\:\:\:\:\:\:\:\:\:\:\:\:其他\end{matrix}\right.
$$

$$
F\left(x;\theta\right)=\left\{\begin{matrix}1-e^{-\dfrac{x^{2}}{\theta}}\:\:\:x\geqslant0\\ 0\:\:\:\:\:\:\:\:\:\:\:\:\:\:\:\:其他\end{matrix}\right.
$$

$$
f\left(x;\theta\right)=\dfrac{2x}{\theta}e^{-\dfrac{x^{2}}{\theta}}\:\:\:\left(x>0\right)
$$

$$
E\left(X\right)=\int_{0}^{\infty}\dfrac{2x^{2}}{\theta}e^{-\dfrac{x^{2}}{\theta}}dx=\dfrac{2}{\theta}\cdot\dfrac{1}{2}\cdot\dfrac{1}{2\cdot\dfrac{1}{\theta}}\sqrt{\dfrac{\pi}{\dfrac{1}{\theta}}}=\dfrac{\sqrt{\pi\cdot\theta}}{2}
$$

$$
E\left(X^{2}\right)=\int_{0}^{\infty}\dfrac{2x^{3}}{\theta}e^{-\dfrac{x^{2}}{\theta}}dx\:\xrightarrow[du=2xdx]{令u=x^{2}}\int_{0}^{\infty}\dfrac{u}{\theta}e^{-\dfrac{u}{\theta}}du=\dfrac{1}{\theta}\cdot\dfrac{1}{\left(\dfrac{1}{\theta}\right)^{2}}=\theta
$$

$$
L\left\lbrack cos\left(\omega x\right)\right\rbrack=\dfrac{s}{s^{2}+\omega^{2}}\:\:\:\:,\:\:\:\:L\left\lbrack sin\left(\omega x\right)\right\rbrack=\dfrac{\omega}{s^{2}+\omega^{2}}\:
$$

$$
L\left\lbrack sin\left(\omega x\right)\right\rbrack=\int_{0}^{\infty}sin\left(\omega x\right)\cdot e^{-sx}dx\:\:\:\:L\left\lbrack cos\left(\omega x\right)\right\rbrack
$$

$$
\int e^{ax}\cdot sin\left(bx\right)dx=\dfrac{1}{a^{2}+b^{2}}\begin{vmatrix}\left(e^{ax}\right)^{\prime} & \left(sin\left(bx\right)\right)^{\prime}\:\\ e^{ax} & sin\left(bx\right)\end{vmatrix}+C\:\:
$$

$$
L\left(x\cdot cos\left(\omega x\right)\right)=\dfrac{s^{2}-\omega^{2}}{\left(s^{2}+\omega^{2}\right)^{2}}\:\:,\:\:\:\:L\left(x\cdot sin\left(\omega x\right)\right)=\dfrac{2\omega s}{\left(s^{2}+\omega^{2}\right)^{2}}
$$

$$
L\left(x\cdot sin\left(\omega x\right)\right)=-\dfrac{d}{ds}L\left(sin\left(\omega x\right)\right)=-\dfrac{d}{ds}\left\lbrack\dfrac{\omega}{s^{2}+\omega^{2}}\right\rbrack即得
$$

$$
y^{\prime\prime}-3y^{\prime}+2y=2e^{3x}\:\:,\:\:y\left(0\right)=y^{\prime}\left(0\right)=0
$$

$$
s^{2}L\left(y\right)-3sL\left(y\right)+2L\left(y\right)=\dfrac{2}{s-3}
$$

$$
L\left(y\right)=\dfrac{2}{\left(s-1\right)\left(s-2\right)\left(s-3\right)}=\dfrac{1}{s-1}+\dfrac{-2}{s-2}+\dfrac{1}{s-3}
$$

$$
y=e^{x}-2e^{2x}+e^{3x}\:\:\:ax^{2}+bx+c
$$

$$
\dfrac{f}{P\cdot Q}=\dfrac{f_{1}}{P}+\dfrac{f_{2}}{Q}\:\:f_{1}=\dfrac{f}{Q}
$$
