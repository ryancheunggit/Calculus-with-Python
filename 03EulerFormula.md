#欧拉公式
在[2.1](01Functions.md)中给出了指数函数的多项式形式：
$$e^x =1+\frac{x}{1!}+\frac{x^2}{2!}+\dots = \sum_{k = 0}^{\infty}\frac{x^k}{k!}$$ 

接下来我们不仅暂时不去解释上式是如何来的，而是丢给读者两个类似的式子：

$$sin(x) = \frac{x}{1!}-\frac{x^3}{3!}+\frac{x^5}{5!}-\frac{x^7}{7!}+\dots = \sum_{k = 0}^{\infty}{(-1)}^k\frac{x^{(2k+1)}}{(2k+1)!}$$
$$cos(x) = \frac{x^0}{0!}-\frac{x^2}{2!}+\frac{x^4}{4!}-\frac{x^6}{6!}+\dots = \sum_{k = 0}^{\infty}{(-1)}^k\frac{x^{2k}}{(2k)!}$$

在高中数学中，我们都接触过**虚数(Imaginary Number)**的概念，这里我们对其来源和意义暂不讨论，只是简单回顾一下其基本的运算规则：
$$i^0=1,\quad i^1=i,\quad i^2=-1,\quad i^3=-i$$
$$i^4=1,\quad i^5=i,\quad i^6=-1,\quad i^7=-i$$

将$$ix$$带入指数函数的公式中，我们获得：
$$e^{ix}=\frac{(ix)^0}{0!}+\frac{(ix)^1}{1!}+\frac{(ix)^2}{2!}+\frac{(ix)^3}{3!}+\frac{(ix)^4}{4!}+\frac{(ix)^5}{5!}+\frac{(ix)^6}{6!}+\frac{(ix)^7}{7!}+\dots$$
$$\qquad =\frac{i^0x^0}{0!}+\frac{i^1x^1}{1!}+\frac{i^2x^2}{2!}+\frac{i^3x^3}{3!}+\frac{i^4x^4}{4!}+\frac{i^5x^5}{5!}+\frac{i^6x^6}{6!}+\frac{i^7x^7}{7!}+\dots$$
$$\qquad = 1\frac{x^0}{0!}+i\frac{x^1}{1!}-1\frac{x^2}{2!}-i\frac{x^3}{3!}+1\frac{x^4}{4!}+i\frac{x^5}{5!}-1\frac{x^6}{6!}-i\frac{x^7}{7!}+\dots$$


