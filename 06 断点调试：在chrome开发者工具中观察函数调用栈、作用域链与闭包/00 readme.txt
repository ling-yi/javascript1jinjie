1 闭包理解：
	闭包形成的条件：
		*在函数内部创建新的函数；
		*新的函数在1执行时，访问了函数的变量对象

2 闭包理解进化版：
	闭包是指这样的作用域，它包含有一个调用这个作用域所封闭的变量、函数等内容的函数（a）。这时，当其他这个作用域内的没有调用这个作用域所封闭的变量、函数等内容的函数执行时也会形成闭包。