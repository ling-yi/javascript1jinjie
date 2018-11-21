1 Promise的作用：
	1)为了解决Ajax的“回调地狱”问题。这也是Promise初次出现的原因
	2)将数据请求与数据处理明确的区分开来，让代码更加具有可读性和课维护性

2 Promise的基础知识：
	2.1.Promise对象有三种状态，分别是：
		1)pedding:等待中，或者进行中，表示还没有得到结果
		2)resolved(Fulfiilled):已经完成，表示得到了我们想要的结果，可以继续往下执行
		3)rejected:也表示得到结果，但是由于结果并非我们所言，因此拒绝执行
	这三种状态不受外界影响，而且状态只能从pedding改变为resolved或者rejected,并且不可逆。在Promise对象的构造函数中，将一个函数作为第一个参数。而这个函数，就是用来处理Promise的状态变化，这个函数的参数resolve和reject都是函数，它们的作用分别是将Promise的状态修改为resolved和rejected。
		
	2.2 关于Proimise的then方法
		Promise对象中的then方法，可以接受构造函数中处理的状态变化，并分别对应执行。then方法有2个参数，第一个参数接受resolved状态的执行，第二个参数接受rejected状态的执行。
		then方法的执行结果也会返回一个Promise对象。因此我们可以进行过then的链式执行，这也是解决回调地狱的只要方式。
		then(null,function(){})等同于catch(function(){})
		
	2.3 Promise中的数据传递
		resolve函数和reject函数和then里面的函数返回的结果将作为下一个then的函数的参数
		
	2.4 Promise.all
		Promise.all接收一个Promise对象组成的数组作为参数，当这个数组所有的Promise对象状态都变成resolved或者或其中一个变成rejected的时候，它才会去调用then方法。
		
	2.5 Promise.race
		Promise.race是以一个Promise对象组成的数组作为参数，当这个数组中的其中一个Promise对象状态变成resolved或者rejected时，就会调用then方法。