
## Arch

- [`syscall-table`](https://github.com/os-module/syscall-table.git) 统一系统调用
- [`PLIC`](https://github.com/os-module/plic) riscv plic
- [`kernel-sync`](https://github.com/os-module/kernel-sync.git) 内核锁的实现，兼容lock-api
  
## Memory Management

- [`pager`](https://github.com/os-module/pager) 此仓库包含两个页帧分配器实现：`Buddy` 与 `Bitmap`
- [`talc`](https://crates.io/crates/talc)Talc is a performant and flexible memory allocator, with first class support for no_std and WebAssembly.
- [`buddy_system_allocator`](https://crates.io/crates/buddy_system_allocator)An (almost) drop-in replacement for phil-opp/linked-list-allocator. But it uses buddy system instead.
- [`rslab`](https://crates.io/crates/rslab) 一个简单的slab分配器实现
## FS
- [`vfscore`](https://github.com/os-module/rvfs.git) 虚拟文件系统相关的的trait定义以及一些有用的数据结构和方法
  - devfs
  - dynfs(be procfs/sysfs)
  - ramfs
  - fat-vfs


## Board

- [`visionfive2-sd`](https://github.com/os-module/visionfive2-sd.git) The [VisionFive2](https://www.starfivetech.com/en/site/boards) SD driver

## Driver

- [`virtio-drivers`](https://github.com/rcore-os/virtio-drivers) VirtIO guest drivers in Rust. For **no_std** environment.
- [`rtc`](https://github.com/os-module/rtc.git) RTC device 

- [`uart8250`](https://github.com/os-module/uart-rs.git) UART8250 Driver


## Other Tools
- [`smpscheduler`](https://github.com/os-module/smpscheduler.git) 简单的多核调度器
- [`tracer`](https://github.com/os-module/tracer) 该工具是一个用于获取内核堆栈回溯信息的实用程序。它可以帮助您识别内核崩溃或故障的根本原因，从而更容易解决问题。
- [`preprint`](https://crates.io/crates/preprint) 类似于log,用于在一些可能需要打印内容的模块中

- [`pconst`](https://github.com/os-module/pconst.git) 系统调用参数的相关数据结构