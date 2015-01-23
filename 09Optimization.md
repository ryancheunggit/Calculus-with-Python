#优化
##**优化问题（Optimization Problem）**     

很多时候，我们用函数来描述一些我们所关心的问题,例如：    
用一张给定边长$$4$$的正方形纸来折一个没有盖的纸盒，设纸盒的底部边长为$$l$$，纸盒的高为$$\frac{4-l}{2}$$，那么纸盒的体积为：  
$$V(l)=l^2\frac{4-l}{2}$$     
我们会希望知道怎样才能使得纸盒的容积最大，也就是关心在$$l>0,4-l>0$$,的限制条件下，函数$$V(l)$$的最大值是多少。   
```
	plt.figure(1, figsize=(6,6))
	plt.axis('off')
	plt.axhspan(0,1,0.2,0.8,ec = "none")
	plt.axhspan(0.2,0.8,0,0.2,ec = "none")
	plt.axhspan(0.2,0.8,0.8,1,ec = "none")

	plt.axhline(0.2,0.2,0.8,linewidth = 2, color = 'black')
	plt.axvline(0.2,0.17,0.23,linewidth = 2, color = 'black')
	plt.axvline(0.8,0.17,0.23,linewidth = 2, color = 'black')

	plt.axvline(0.2,0.8,1,linewidth = 2, color = 'black')
	plt.axhline(0.8,0.17,0.23,linewidth = 2, color = 'black')
	plt.axhline(1,0.17,0.23,linewidth = 2, color = 'black')

	plt.text(0.495,0.22,r"$l$", fontsize = 18,color="black")
	plt.text(0.1,0.9,r"$\frac{4-l}{2}$", fontsize = 18,color="black")

	plt.show()
```
![09-01Box](images/09-01Box.png)    
 
通过观察函数图，不难得出这个问题的答案：    
```
		l = np.linspace(0,4,100)
		V = lambda l: 0.5*l**2*(4-l)
		plt.plot(l,V(l))
```
![09-02 Volume](images/09-02Volume.png)     

##**关键点（Critical Points）**  
通过导数一节，我们知道一个函数在某处的导数所描述的是：当输入值在该位置附近变化时，函数值所发生的相应变化。  
因此，如果给定一个函数$$f$$，如果知道在点$$x=a$$处函数的导数不为$$0$$，则在该点出稍微改变函数的输入值，函数值都会变化。相反，如果函数$$f$$在点$$x=a$$处函数的导数为$$0$$，那么这个点就被称为关键点。    