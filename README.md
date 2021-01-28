# proj59-linux-fast-scheduler

### 项目名称
Linux 内核低时延调度器

### 项目描述

CFS 越来越臃肿, 对终端以及小型系统不太友好

其主要存在的问题:

*	CFS 体现完全公平, 缺乏针对关键线程的优先供给;
*	CFS 本身并不严格保证时延, 因此对时延敏感型的进程不友好;
*	由于 CFS 本身的越来越硬肿, 在开启组调度之后, 负载计算以及更新本身引入的开销越来越大.


该项目调度器目标:

1.	适用于终端、车载以及云等场景;
2.	支持对指定数量关键进程的优先调度, 这些线程可以抢占其他非关键进程;
3.	在 2 的基础上, 进一步达成极低的调度延迟和唤醒延迟, 不同进程可以指定延时的 QOS, 调度器将尽可能的满足调度的 QOS 需求.


### 所属赛道

2021全国大学生操作系统比赛的"内核实现"赛道




### 参赛要求

- 以小组为单位参赛，最多三人一个小组，且小组成员是来自同一所高校的本科生（2021年春季学期或之后本科毕业的大一~大四的学生）
- 如学生参加了多个项目，参赛学生选择一个自己参加的项目参与评奖
- 请遵循"2021全国大学生操作系统比赛"的章程和技术方案要求



### 项目导师

谢秀奇、[成坚](https://kernel.blog.csdn.net)

* [Xie XiuQi](https://gitee.com/xiexiuqi), [Cheng Jian](https://github.com/gatieme)

* email xiexiuqi@huawei.com, cj.chengjian@huawei.com


### 难度


中等



### 特征


*	确定时延调度

*	调度时延、切换时延优于 CFS

### 文档

[sched: Add micro quanta scheduling class](https://lkml.org/lkml/2019/9/6/178)

[Task latency-nice](https://lore.kernel.org/patchwork/cover/1122405)



### License

* [GPL-2.0](https://opensource.org/licenses/GPL-2.0)



## 预期目标

### 注意：下面的内容是建议内容，不要求必须全部完成。选择本项目的同学也可与导师联系，提出自己的新想法，如导师认可，可加入预期目标

### 基于 Linux kernel 4.19 或 5.10 或社区主线实现

* 描述算法思路, 实现相关算法, 可以编译安装运行

* 提供与 RT/CFS 等调度器在时延方面的测试数据

* 补丁发送到社区主线(可选)
