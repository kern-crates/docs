### 待完成任务

1. NoPreemt组件放到操作层与资源层之间
NoPreempt(kernel_guard)与Mutex(axsysn)并列。解决关闭抢占这部分的反向依赖。

2. axmount组件的进一步拆分
把fs模块拆出来，放到crates目录下面，作为一个单独的组件。fs模块的位置应该在file组件之下，当然也是在资源层之下。

3. Aarch64支持
能够如riscv64启动/sbin/init，验证HAL相关部分的剥离"干净"。
当前问题：riscv64从内核切换到用户态这步不对。

4. 通过syscall 对应用支持fork/clone
为支持外部测试用例做准备

5. 启动过程中，支持Linux cmdline
有选择的屏蔽/sbin/init，可以抢先执行sh或特定testcase。
为支持外部测试用例做准备

6. 引入LTP(Linux Test Project)
通过glibc和syscall访问的黑盒测试框架

7. 组件及接口测试
组件级测试，先从fork这条路上涉及的组件开始，每个组件一个测试用例，验证组件基本功能和接口合规。


### 已完成任务

1. trap/irq/syscall从axhal拆分
axtrap组件位于mkboot和axsyscall两个层次之间。解决这部分的反向依赖。
已经实验，从axhal拆分出axtrap处理except/irq/syscall，位置接近最顶层，在mkboot和axsyscall之间位置。

2. boot组件拆分from axhal
boot顶级组件 -> mkboot(axruntime) -> (app)。。解决boot这部分的反向依赖。
