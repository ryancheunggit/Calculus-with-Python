#泰勒级数
##**泰勒级数(Taylor Series)**  
在前几章的预热之后，读者可能会有这样的疑问，是否任何函数都可以写成友善的多项式形式呢？目前为止，我们介绍的$$e^x,sin(x),cos(x)$$都有其奇妙的多项式形式。这些多项式形式被称为对应函数在$$x=0$$处展开的泰勒级数。  

下面我们给出函数$$f(x)$$在$$x=0$$处展开的泰勒级数的定义：  
$$f(x)=f(0)+\frac{f'(0)}{1!}x+\frac{f''(0)}{2!}x^2+\frac{f'''(0)}{3!}x^3+\dots=\sum_{k=0}^{\infty}\frac{f^{(k)}(0)}{k!}x^k$$  
其中：$$f^{(k)}(0)$$表示函数$$f$$的$$k$$次导函数在点$$x=0$$处的取值。  

我们知道对$$e^x$$无论计算多少次导数结果都是$$e^x$$，即：
$$exp'(x)=exp''(x)=exp'''(x)=\dots=exp^{(k)}(x)=exp(x)$$  
$$exp'(0)=exp''(0)=exp'''(0)=\dots=exp^{(k)}(0)=exp(0)=1$$    
因而：
$$exp(x)=exp(0)+\frac{exp'(0)}{1!}x+\frac{exp''(0)}{2!}x^2+\frac{exp'''(0)}{3!}x^3+\dots$$
$$\qquad =1 + \frac{x}{1!}+\frac{x^2}{2!}+\frac{x^3}{3!}+\dots$$
$$\qquad =\sum_{k=0}^{\infty}\frac{x^k}{k!}$$  
便得到了在[2.1](01Functions.md)中所介绍的公式。  

类似地，有兴趣的读者可以尝试用泰勒级数的定义来推导一下$$sin(x),cos(x)$$关于$$x=0$$处展开的泰勒级数。  

下面，在Python中试试吧：
```
    import sympy 
    # 指定x为符号
    x = sympy.Symbol('x')
    # exp为公式
    exp = e**x
    # 下面开始求和,就求前21项的和吧
    sums = 0
    for i in range(20):
        # 求i次导函数
        numerator = exp.diff(x,i)
        # 计算导函数在x=0处的值
        numerator = numerator.evalf(subs={x:0})
        denominator = np.math.factorial(i)
        sums += numerator/denominator*x**i
    # 下面检验一下原始的exp函数和其在x=0处展开的泰勒级数前20项之和的差距
    xvals = np.linspace(0,20,100)
    for xval in xvals:
        plt.plot(xval,exp.evalf(subs={x:xval}),'bo',\
                 xval,sum.evalf(subs={x:xval}),'ro')
```

![04-01 approx](images/04-01approx.png)  

表明前指数函数$$e^x$$在$$x=0$$处展开的泰勒级数只取前20项的话，在输入较小时（我会觉得<15），能够很好地用来近似$$e^x$$
##**多项式近似式**