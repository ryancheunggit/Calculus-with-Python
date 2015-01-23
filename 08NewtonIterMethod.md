#牛顿迭代法
##**求二次根**  
各位同学可能遇到过这样的编程题目，要求在不使用$$x^{\frac{1}{2}}$$或$$\sqrt{x}$$的前提下，求方程$$x^2=C$$的正根。  
可以用牛顿迭代法解：  
```
	def mysqrt(c, x = 1, maxiter = 10, prt_step = False):
	    for i in range(maxiter):
	        x = 0.5*(x+ c/x)
	        if prt_step == True:
	            print "After {0} iteration, the root value is updated to {1}".format(i+1,x)
	    return x
	    
	print mysqrt(2)
	# result : 1.414213562373095
```

根据上一节介绍的线性近似：  
$$f(x+h)\approx f(x)+f'(x)h$$ 
如果$$x+h$$是$$f(x)=0$$的一个根，即$$f(x+h)=0$$，因此：  
$$h\approx -1\frac{f(x)}{f'(x)}$$

要理解这个方法，下面又到了喜闻乐见的绘图时间
