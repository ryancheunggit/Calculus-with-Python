#欧拉公式
##**欧拉公式（Euler's Formula）**
在[2.1](01Functions.md)中给出了指数函数的多项式形式：
$$e^x =1+\frac{x}{1!}+\frac{x^2}{2!}+\dots = \sum_{k = 0}^{\infty}\frac{x^k}{k!}$$ 

接下来我们不仅暂时不去解释上式是如何来的，而是丢给读者两个有关三角函数的类似式子：

$$sin(x) = \frac{x}{1!}-\frac{x^3}{3!}+\frac{x^5}{5!}-\frac{x^7}{7!}+\dots = \sum_{k = 0}^{\infty}{(-1)}^k\frac{x^{(2k+1)}}{(2k+1)!}$$
$$cos(x) = \frac{x^0}{0!}-\frac{x^2}{2!}+\frac{x^4}{4!}-\frac{x^6}{6!}+\dots = \sum_{k = 0}^{\infty}{(-1)}^k\frac{x^{2k}}{(2k)!}$$

在高中数学中，我们都接触过**虚数(Imaginary Number)**的概念，这里我们对其来源和意义暂不讨论，只是简单回顾一下其基本的运算规则：
$$i^0=1,\quad i^1=i,\quad i^2=-1,\quad i^3=-i$$
$$i^4=1,\quad i^5=i,\quad i^6=-1,\quad i^7=-i$$

将$$ix$$带入指数函数的公式中，我们获得：
$$e^{ix}=\frac{(ix)^0}{0!}+\frac{(ix)^1}{1!}+\frac{(ix)^2}{2!}+\frac{(ix)^3}{3!}+\frac{(ix)^4}{4!}+\frac{(ix)^5}{5!}+\frac{(ix)^6}{6!}+\frac{(ix)^7}{7!}+\dots$$
$$\qquad =\frac{i^0x^0}{0!}+\frac{i^1x^1}{1!}+\frac{i^2x^2}{2!}+\frac{i^3x^3}{3!}+\frac{i^4x^4}{4!}+\frac{i^5x^5}{5!}+\frac{i^6x^6}{6!}+\frac{i^7x^7}{7!}+\dots$$
$$\qquad = 1\frac{x^0}{0!}+i\frac{x^1}{1!}-1\frac{x^2}{2!}-i\frac{x^3}{3!}+1\frac{x^4}{4!}+i\frac{x^5}{5!}-1\frac{x^6}{6!}-i\frac{x^7}{7!}+\dots$$
$$\qquad = (\frac{x^0}{0!}-\frac{x^2}{2!}+\frac{x^4}{4!}-\frac{x^6}{6!}+\dots)+i(\frac{x}{1!}-\frac{x^3}{3!}+\frac{x^5}{5!}-\frac{x^7}{7!}+\dots)$$
$$\qquad = cos(x)+isin(x)$$

此时，我们便获得了著名的欧拉公式：$$e^{ix} = cos(x)+isin(x)$$  
特别地，将$$x=\pi$$时：$$e^{i\pi}+1=0$$  

欧拉公式在三角函数、圆周率、虚数以及自然指数之间建立的桥梁，在很多领域都扮演着重要的角色。

如果你对欧拉公式的正确性感到疑惑，不妨在Python中验证一下：   
```
    x = np.linspace(-np.pi,np.pi)    
    # Python中虚数用j表示
    lhs = e**(1j*x)
    rhs = cos(x)+1j*sin(x)
    print sum(lhs==rhs)==len(x)
    True
```

将函数写成多项式形式有很多的好处，多项式的微分和积分都比较容易。现在你知道了$$e^x,sin(x),cos(x)$$的多项式形式，不妨用其去验证一下中学书本中强行填塞给你这几个公式：   
$$\frac{d}{dx}e^x=e^x$$
$$\frac{d}{dx}sin(x)=cos(x)$$
$$\frac{d}{dx}cos(x)=-sin(x)$$  

喔，对了，这一章怎能没有图呢？收尾前来一发吧：
```
    for p in e**(1j*x):
        plt.polar([0, angle(p)],[0, abs(p)], marker = 'o')
```   
![03-01 polar with complex](images\03-01polar.png)

