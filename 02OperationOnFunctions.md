#函数的复合
##**函数的复合（Composition）**:  
函数$$f$$和$$g$$的复合:$$f\circ g(x)=f(g(x))$$，可以理解为首先将$$x$$输入给函数$$g$$获得输出$$g(x)$$后将其进而输入给函数$$f$$，最终获得结果$$f(g(x))$$。

+ 几个函数的复合结果仍然是一个函数:接受输入，给出输出
+ 任何函数都可以看成是若干个函数的复合 
+ $$f\circ g(x)$$的定义域与$$g$$的定义域相同，但值域不一定与$$f$$的值域相同。


例如:$$f(x)= x+1,g(x)=x^2,h(x)=x^2+1$$,函数$$h$$可以视为$$f$$和$$g$$复合后的结果。$$f$$的值域为$$\mathbb{R}$$，但$$h$$的值域为$$(1,\infty)$$ 

在Python中我们可以很直观地对函数进行复合：

```
    def f(x):
        return x+1
    
    def g(x):
        return x**2
        
    def h(x):
        return f(g(x))
        
    x = np.array(range(-10,10))
    
    # 这里我们使用了Python的list comprehension来计算y
    y = np.array([h(i) for i in x])
    
    # 'bo' 将表示我们会使用蓝色的圆圈绘制点图，而非默认的线图
    plt.plot(x, y, 'bo')
```

![02-01 compFunc](images/02-01compFunc.png)    

我们也可以使用Python的lambda函数功能来简明地定义$$h$$:

```
    h2 = lambda x: f(g(x))
    plt.plot(x,h2(x),'rs')
```

![02-02 compFunc2](images/02-02compFunc2.png) 

##**逆函数（Inverse Function）**:  
给定一个函数$$f$$，其逆函数$$f^{-1}$$是一个与$$f$$进行复合后会得到$$f\circ f^{-1}(x)=f^{-1} \circ f (x)=x$$的特殊函数。

函数与其反函数的函数图一定是关于直线$$y=x$$对称的：
```
    w = lambda x: x**2
    winv = lambda x: sqrt(x)
    x = np.linspace(0,2,100)
    plt.plot(x, w(x),'b',x,winv(x),'r',x,x,'g_.')
```
![02-03 inverse](images/02-03inverse.png) 


