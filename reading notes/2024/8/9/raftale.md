线程安全的三种方式：
ⅰ. 不共享状态变量：线程封闭，如threadLocal；
ⅱ. 将状态变量修改为不可变的变量：只读共享，不共享写。
ⅲ. 访问状态变量时使用同步：阻塞加锁或者无锁算法