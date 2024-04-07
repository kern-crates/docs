### 任务列表


- [x] trap/irq/syscall从axhal拆分

axtrap组件位于mkboot和axsyscall两个层次之间。解决这部分的反向依赖。

已经实验，从axhal拆分出axtrap处理except/irq/syscall，位置接近最顶层，在mkboot和axsyscall之间位置。



- [ ] boot组件拆分

boot顶级组件 -> mkboot(axruntime) -> (app)。。解决boot这部分的反向依赖。



- [ ] NoPreemt组件放到操作层与资源层之间

NoPreempt(kernel_guard)与Mutex(axsysn)并列。解决关闭抢占这部分的反向依赖。



- [ ] axmount组件的进一步拆分

把fs模块拆出来，放到crates目录下面，作为一个单独的组件。fs模块的位置应该在file组件之下，当然也是在资源层之下。



- [ ] Aarch64支持

能够运行，验证HAL相关部分的剥离"干净"。

当前问题：从内核切换到用户态这步不对。

