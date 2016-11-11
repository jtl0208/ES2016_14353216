##Deadlock
####实验截图

![deadlock.png](http://upload-images.jianshu.io/upload_images/3250630-e820a096328ec098.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

####产生死锁的四个条件
 * 互斥条件：一个资源每次只能被一个进程使用
 * 请求和保持：一个进程在折你去哪个新的资源的同时保持对原有资源的占有
 * 不可强占：资源申请者不可强行从资源占有者手中夺取资源，资源只能由占有者自愿释放
 * 循环等待：存在一个进程等待队列

####死锁原因
run函数先执行b.methodB()函数，接着是准备请求A类的资源，但此时main函数延时结束进入methodA，相当于拥有了A资源，打算请求B类资源。因为b.methodB属于B类，还我在run函数手中，所以主线程被阻塞，a.last属于A类资源，还握在main函数手中所以线程t被阻塞死锁发生。
