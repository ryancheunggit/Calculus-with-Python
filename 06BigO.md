#大O记法
我们已经见过了很多函数，在比较两个函数时，我们可能会想知道，随着输入值$$x$$的增长或者减少，两个函数的输出值增长或减少的速度究竟谁快谁慢，那一个函数最终会远远甩开另一个。  

通过绘制函数图，显然是可行的方法：    
```
	x = range(1,7)

	factorial = [np.math.factorial(i) for i in x]
	exponential = [np.e**i for i in x]
	polynomial = [i**3 for i in x]
	logarithmic = [np.log(i) for i in x]

	plt.plot(x,factorial,'black',\
    	     x,exponential, 'blue',\
        	 x,polynomial, 'green',\
         	 x,logarithmic, 'red')
```

