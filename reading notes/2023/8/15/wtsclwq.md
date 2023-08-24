## 第四章 保护模式

### 为什么要有保护模式？

实模式的**安全缺陷**：

（1）实模式下操作系统和用户程序属于同一特权级。 

（2）用户程序所引用的地址都是指向真实的物理地址，也就是说逻辑地址等于物理地址。 

（3）用户程序可以自由修改段基址。

实模式的**功能缺陷**：

（4）访问超过 64KB 的内存区域时要切换段基址。 

（5）一次只能运行一个程序，无法充分利用计算机资源。 

（6）共 20 条地址线，最大可用内存为 1MB，这即使在 20 年前也不够用。

> 我们说实模式时，指的是 32 位的 CPU 运行在 16 位模式下的状态，不是 CPU 变身 成纯粹的 16 位

###  保护模式的寄存器扩展

所以，为了让一个寄存器就能访问 4GB 空间，需要寄存器宽度提升到 32 位。 **除段寄存器外**，通用寄存器、指令指针寄存器、标志寄存器都由原来的 16 位扩展到了 32 位。
