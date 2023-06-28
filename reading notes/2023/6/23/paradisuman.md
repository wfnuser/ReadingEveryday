
| 步骤 | 描述 |
| --- | --- |
| 用户-内核转换 | 从旧进程的内核线程进行系统调用或中断。 |
| 上下文切换到调度器线程 | 将上下文切换到当前CPU的调度器线程。 |
| 上下文切换到新进程的内核线程 | 切换到新进程的内核线程。 |
| 陷阱返回至用户级进程 | 从新进程的内核线程返回至用户级进程。 |
| 保存旧线程的CPU寄存器 | 在进行线程切换时，需要保存旧线程的CPU寄存器。 |
| 恢复新线程的寄存器 | 在进行线程切换时，需要恢复新线程之前保存的寄存器。 |
| swtch函数执行保存和恢复 | swtch函数负责进行内核线程切换的保存和恢复操作。 |
| 内核线程调用swtch | 当一个进程需要放弃CPU时，它的内核线程会调用swtch来保存它自己的上下文并返回到调度器上下文。 |
| swtch只保存被调用者保存的寄存器 | swtch函数只保存被调用者保存的寄存器；C编译器在调用者中生成代码以在栈上保存调用者保存的寄存器。 |
| 调度器调用swtch切换到cpu->scheduler | sched调用swtch以切换到每个CPU的调度器上下文。这个上下文是在过去的某个时刻保存的，当调度器调用swtch切换到现在正在放弃CPU的进程时。 |