## 编写MBR主引导记录

### BIOS

BIOS 全称叫 Base Input & Output System，即基本输入输出系统。

为什么被称为**基本**输入输出？

- 硬件本身提供了一些初始化的功能调用，BIOS 可以直接调用。
- BIOS 还做了一件伟大的事情，建立了中断向量表，这样 就可以通过“int 中断号”来实现相关的硬件调用。
- 由于64KB 大小的空间，不可能把所有硬件的 IO 操作实现得面面俱到，而且也没必要实现那么多，这就是 BIOS 称为基本输入输出系统的原因。

![image-20230726094111769](https://wtsclwq.oss-cn-beijing.aliyuncs.com/image-20230726094111769.png)

实模式下1MB的内存布局如上图（CPU能够访问到的所有地址范围），`0~0x9FFFF`的64KB存储的是BIOS代码，其中最后16B存储的是BIOS代码的入口地址，存储了一条指令`jmp f000: e05b`

> 为什么地址范围的大小比物理内存更大？
>
> - 在计算机中，并不是只有咱们插在主板上的内存条需要通过地址总线访问。
> - 物理内存多大都没用， 主要是看地线总线的宽度。 还要看地址总线的设计， 是不是全部用于访问 DRAM。
> - CPU 能够访问一 个地址，这是地址总线给做的映射，相当于给该地址分配了一个存储单元，而该存储单元要么落在某个 rom 中，要么落到了某个外设的内存中，要么落到了物理内存条上。
>
> <img src="https://wtsclwq.oss-cn-beijing.aliyuncs.com/image-20230726095548412.png" alt=" " style="zoom:50%;" />

### 唤醒BIOS

BIOS被存储在主板上的一块的ROM中，也就是被被映射在`0xF0000~0xFFFFF`的那一部分。
