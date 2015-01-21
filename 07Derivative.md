#导数
##**切线（Tangent line）**  
中学介绍导数的时候，通常会举两个例子，一个是物理中的例子：对路程的时间函数$$s(t)$$求导可以得到速度的时间函数$$v(t)$$，再进一步求导可以得到加速度的时间函数$$a(t)$$；或者几何意义上的例子：对函数关于某一点进行求导，得到的是函数该点处切线的斜率。  
选中函数图像中某一点，然后不断地将函数图放大，当我们将镜头拉至足够近后便会发现函数图看上去像一条直线，这条直线就是切线。  
```
	from sympy.abc import x
	# 函数
	f = x**3-2*x-6
	# 在x=6处正切于函数的切线
	line = 106*x-438

	d1 = np.linspace(2,10,1000)
	d2 = np.linspace(4,8,1000)
	d3 = np.linspace(5,7,1000)
	d4 = np.linspace(5.8,6.2,100)
	domains = [d1,d2,d3,d4]

	# 画图的函数
	def makeplot(f,l,d):
	    plt.plot(d,[f.evalf(subs={x:xval}) for xval in d],'b',\
	             d,[l.evalf(subs={x:xval}) for xval in d],'r')

	for i in range(len(domains)):
		# 绘制包含多个子图的图表
	    plt.subplot(2, 2, i+1)
	    makeplot(f,line,domains[i])

	plt.show()
```
![07-01 tangentline](images/07-01tangline.png)  

在两个例子的背后，导数真正关心的事是：当我们稍微改变一点函数的输入值时，函数的输出值会有怎样变化。    

##**导数（Derivative）**  
导数的定义如下：   
定义1：  
$$f'(a)=\frac{df}{dx}\bigg|_{x=a}=\lim_{x\rightarrow a}\frac{f(x)-f(a)}{x-a}$$   
若该极限不存在，则函数在$$x=a$$处的导数不存在。  

定义2：  
$$f'(a)=\frac{df}{dx}\bigg|_{x=a}=\lim_{h\rightarrow 0}\frac{f(a+h)-f(a)}{h}$$    
若该极限不存在，则函数在$$x=a$$处的导函数不存在。  

以上两个定义都是耳熟能详的定义了，就不多说了。  
定义3：  
函数$$f(x)$$在$$x=a$$处的导数$$f'(a)$$是满足如下条件的常数$$C$$:    
对于$$x$$在$$a$$附近的任意变化$$h$$($$h=x-a$$)，$$f(a+h)-f(a)=Ch+O(h^2)$$始终成立。 
也就是说导数$$C$$是输出值变化中一阶项的系数。    

如果难以理解的话，对上式两边同时除以$$h$$并同时取极限可以得到：   
$$\lim_{h\rightarrow 0}\frac{f(a+h)-f(a)}{h}=\lim_{h\rightarrow 0}C+O(h)$$  
便应该可以理解了吧，为何导数$$f'(a)=C$$可以这样定义了。    

也可以这么写：  
$$f(x+h)=f(x)+\frac{df}{dx}h+O(h^2)$$  
导数

