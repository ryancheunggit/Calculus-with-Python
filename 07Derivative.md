#导函数
##**切线（Tangent line）**  
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