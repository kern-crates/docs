# docs
操作系统由一系列子系统构成，而这些子系统由更小的模块构成。传统的操作系统开发倾向与将这些小模块包含在内核代码库当中，这导致了其他人想借鉴一些实现不得不拷贝相关的代码。我们希望这些小模块是独立的，松耦合的，在`rust`的世界当中，我们希望这些模块是一个`crate`，这可以带来极大的可重用性，并且因为是独立的模块，新的改进将更加容易。当然，将内核中的一些模块抽离出来形成一个独立的模块可能因为模块与内核的复杂联系而存在较大的困难，但我们尽可能地去完成这一构想。

更多内容参考: [会议讨论纪要](./docs/meeting_conclusion.md)

这个仓库包含了一系列操作系统模块实现，这些模块覆盖了内存管理、驱动、网络、调度等部分。我们希望收纳来自各位操作系统爱好者的模块实现，同时，其他人可以在这里找到自己需要的模块。

## 组件化工作规划

 - [ ] 组件独立仓库: 石磊,杨金博, 萧络元
 - [ ] 组件完善: 按照[组件合规要求](#组件合规要求)完成合规易用性补充
 - [ ] 组件评审发布: 完成安全、功能、测试评审，组件发布`crates-io`

### 组件合规要求

- 一般性要求(**必须**) 
  - Cargo.toml 要求[发布到crates-io参考](https://course.rs/cargo/reference/publishing-on-crates.io.html)
- 安全要求(**必须**)
  - 避免`unsafe`乱用，符合[unsafe编码规范](https://rust-coding-guidelines.github.io/rust-coding-guidelines-zh/safe-guides/coding_practice/unsafe_rust.html)
  - 必须要使用`unsafe`代码块，需要给出`SAFETY`安全说明
- 文档要求(**非必须建议**)
  - 按照[rustdoc](https://rustwiki.org/zh-CN/rustdoc/what-is-rustdoc.html#%E5%9F%BA%E6%9C%AC%E4%BD%BF%E7%94%A8) 提供更加详细的文档说明
- 测试要求(**非必须建议**)
  - 模块具备独立的单元测试、性能测试

## 组件化OS参考
在这里列出所有的组件化的OS实现参考

| OS | Description | 
|-|-|
| [Alien](./docs/alien.md)||

## 组件清单
在这里列出所有的模块清单

- 架构支持: 
    - [`loongArch64`](https://github.com/Godones/loongArch64) loongArch手册的rust实现 [![](https://img.shields.io/badge/loongArch64-v0.2.2-green.svg)](https://crates.io/crates/loongArch64)
    - [`riscv`](https://github.com/rust-embedded/riscv) [![](https://img.shields.io/badge/riscv-v0.10.1-green.svg)](https://crates.io/crates/riscv)


## Contributing

欢迎各位同学贡献自己的OS模块，按以下步骤添加新的模块。

1. 克隆此仓库
2. 在`docs`目录新建`{your os name}.md`，并参考[Alien](./docs/alien.md)给出您的os中的模块简单描述和链接
3. 在`README`的`Oses`中添加一个条目以指向您新添加的文件
4. create PR 

## Reference

[awesome-embedded-rust](https://github.com/rust-embedded/awesome-embedded-rust)
