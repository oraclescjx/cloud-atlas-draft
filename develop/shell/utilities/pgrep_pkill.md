`pgrep`和`pkill`有些类似，都是基于进程名字和其他一些属性来处理进程的工具。

> `pgrep`虽然使用方便，但是也存在误匹配进程名的可能。因为Linux/Unix允许不同目录使用相同的文件名，或者多个进程名包含相同的关键字，如果恰好匹配上这个关键字，就有可能对并非期望的进程进行误操作。所以，实际在使用中，建议不要使用过于短小简单（易误匹配）的关键字。
>
> `pgrep`有一个`-f`参数可以完整匹配，这个完整匹配是指使用`stat`中完整的命令（包含命令参数）。但这扩大了误匹配的风险，因为所匹配的关键字可能会在命令行参数中出现，对于大量进程，有可能误匹配到进程。

| 选项 | 说明 |
| -signal, --signal <signal> | (只用于`pkill`)，定义发送给符合进程的信号，可以使用信号名或数值 |
| -c, --count | （只用于`pgrep`），不是返回进程号，而是返回匹配名林的数量 |
| -d, --delimiter <delimiter> | （只用于`pgrep`）设置进程输出时候的分隔符号，默认是换行 |
| -f, --full | 通常只匹配进程名，当使用`-f`则完整匹配命令 |
| -g, --pgroup <pgrp,...> | 只匹配列出在进程组id中进程，进程组`0`是传输到`pgrep`或`pkill`自己的进程组 |
| -G, --group <gid,...> | 只匹配实际列出的组id进程 |
| -l, --list-name | （只用于`pgrep`）


# 参考

* [Linux pgrep and pkill command](https://www.computerhope.com/unix/upgrep.htm)