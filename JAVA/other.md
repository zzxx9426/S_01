### linux内核功能

* 一个完整的Linux内核一般由5部分组成，它们分别是内存管理、进程管理、进程间通信、虚拟文件系统和网络接口。

* Linux内核可以划分成3层。
> 最上面是系统调用接口，它实现了一些基本的功能，例如read和write。系统调用接口之下是内核代码，可以更精确地定义为独立于体系结构的内核代码。这些代码是Linux所支持的所有处理器体系结构所通用的。在这些代码之下依赖于体系结构的代码，构成了通常称为BSP（Board Support Package //板级支持包）的部分，这些代码用作给定体系结构的处理器和特定于平台的代码。

* Linux内核的属性

> Linux内核实现了很多重要的体系结构属性。在或高或低的层次上，内核被划分为多个子系统。Linux也可以看作是一个整体，因为它会将所有这些基本服务都集成到内核中。这与微内核的体系结构不同，后者会提供一些基本的服务，例如通信、I/O、内存和进程管理，更具体的服务都是插入到微内核层中的。

*Linux内核的主要子系统  

内核的一个体系结构透视图  

![](https://github.com/zzxx9426/JAVA/blob/master/Linux%E5%86%85%E6%A0%B8%E7%BB%93%E6%9E%84%E9%80%8F%E8%A7%86%E5%9B%BE.png?raw=true)

### 系统调用接口

SCI层提供了某些机制执行从用户空间到内核的函数调用。正如前面讨论的一样，这个接口以来于体系结构，甚至在相同的处理器家族内也是如此。SCI实际上是一个非常有用的函数调用多路复用和多路分解服务。在/.Linux/arch中找到依赖于体系结构的部分。

### 进程管理

进程管理的重点是进程的执行。在内核中，这些进程成为线程，代表了单独的处理器虚拟化（线程代码、数据、堆栈和CPU寄存器）。在用户空间，通常使用进程这个术语，不过Linux实现并没有区分这两个概念（进程和线程）。内核通过SCI提供了一个应用程序编程接口（API）来创建一个新进程（fork、exec或Portable Operating System Interface[POSIX]函数），停止进程（kill、exit），并在他们之间进行通信和同步（signal或者POSIX机制）。
<br>

进程管理还包括处理活动进程之间共享CPU的需求。内核实现了一种新型的调度算法，不管多少个线程在竞争CPU，这种算法都可以在固定时间内进行操作。这种算法就成为O（1）调度程序，这个名字就表示它调度多个线程所使用的时间和调度一个线程所使用的时间是相同的。O（1）调度程序也可以支持多个处理器（成为堆成多处理器或SMP）。你可以在./Linux/lernel中找到进程管理的源代码，在./linux/arch中可以找到依赖于体系结构的源代码。  

### 内存管理

内存所管理的另外一个重要资源是内存。为了提高效率，如果由硬件管理虚拟内存，内存是按照所谓的内存也方式进行管理的（对于大部分体系结构来说都是4KB）。Linux包括了管理可用内存的方式，以及物理和虚拟映射所使用的硬件机制。

不过内存管理要管理的可不止4KB缓冲区。Linux提供了对4KB缓冲区的抽象，例如slab分配器。这种内存管理模式使用4KB缓冲区为基数，然后从中分配结构，并跟踪内存页使用情况，比如哪些内存页是满的，哪些页面没有完全使用，哪些页面为空。这样就允许该模式根据系统需求来动态调整内存使用。

为了支持多个用户使用内存，有时会出现可用内存被消耗光的情况。由于这个原因，页面可以移出内存并放入磁盘中。这个过程为*交换*，因为页面会被从内存交换到硬盘上。内存管理的源代码可以在./linux/mm中找到。  

### 虚拟文件系统

虚拟文件系统（VFS）是Linux内核中非常有用的一个方面，因为它为文件系统提供了一个通用的接口抽象。VFS再SCI和内核所支持的文件系统之间提供了一个交换层。

![](https://github.com/zzxx9426/JAVA/blob/master/%E8%99%9A%E6%8B%9F%E6%96%87%E4%BB%B6%E4%BA%A4%E6%8D%A2%E5%B1%82.png?raw=true)

在VFS上面，是对诸如open、close、read和write之类的函数的一个通用API抽象。在VFS下面是文件系统抽象，它定义了上层函数的实现方式。他们是给定文件系统（超过50个）的插件。文件系统的源代码可以在./linux/fs中找到。

文件系统层之下是缓冲区，它为文件系统层提供了一个通用函数集（与具体文件系统无关）。这个缓存层通过将数据保留一段时间（或者随即预先读取数据以便在需要时就可用）又花了对物理设备的访问。缓冲区缓存之下是设备驱动程序，它实现了特定物理设备的接口。

### 网络堆栈

网络堆栈在设计上遵循模拟协议本身的分层体系结构。回想一下，Internet Protocol（IP）是传输协议（通常称为传输控制协议或TCP）下面的核心网络层协议。TCP上面是socket层，它是通过SCI进行调用的。

socket层是网络子系统的的标注API，它为各种网络协议提供另一个用户接口。从原始帧访问到IP协议数据单元（PDU），再到TCP和 User Datagram Protocol（UDP），socket层提供了一种标准化的方法来管理连接，并在各个重点之间移动数据。内核中网络源代码可以在./linux/net中找到。

### 设备驱动程序

Linux内核中有大量代码都在设备驱动程序中，它们能够运转特定的硬件设备。Linux 源码树提供了一个驱动程序子目录，这个目录又进一步划分为各种支持设备，例如 Bluetooth、I2C、serial 等。设备驱动程序的代码可以在 ./linux/drivers 中找到。


### 依赖体系结构的代码
尽管 Linux 很大程度上独立于所运行的体系结构，但是有些元素则必须考虑体系结构才能正常操作并实现更高效率。./linux/arch 子目录定义了内核源代码中依赖于体系结构的部分，其中包含了各种特定于体系结构的子目录（共同组成了 BSP）。对于一个典型的桌面系统来说，使用的是 i386 目录。每个体系结构子目录都包含了很多其他子目录，每个子目录都关注内核中的一个特定方面，例如引导、内核、内存管理等。这些依赖体系结构的代码可以在 ./linux/arch 中找到。

### Linux 内核的一些有用特性
如果 Linux 内核的可移植性和效率还不够好，Linux 还提供了其他一些特性，它们无法划分到上面的分类中。
作为一个生产操作系统和开源软件，Linux 是测试新协议及其增强的良好平台。Linux 支持大量网络协议，包括典型的 TCP/IP，以及高速网络的扩展（大于 1 Gigabit Ethernet [GbE] 和 10 GbE）。Linux 也可以支持诸如流控制传输协议（SCTP）之类的协议，它提供了很多比 TCP 更高级的特性（是传输层协议的接替者）。
Linux 还是一个动态内核，支持动态添加或删除软件组件。被称为动态可加载内核模块，它们可以在引导时根据需要（当前特定设备需要这个模块）或在任何时候由用户插入。
Linux 最新的一个增强是可以用作其他操作系统的操作系统（称为系统管理程序）。最近，对内核进行了修改，称为基于内核的虚拟机（KVM）。这个修改为用户空间启用了一个新的接口，它可以允许其他操作系统在启用了 KVM 的内核之上运行。除了运行 Linux 的其他实例之外， Microsoft® Windows® 也可以进行虚拟化。惟一的限制是底层处理器必须支持新的虚拟化指令。



//11

### linux 管道 

管道是Linux中很重要的一种通信方式,是把一个程序的输出直接连接到另一个程序的输入,常说的管道多是指无名管道,无名管道只能用于具有亲缘关系的进程之间，这是它与有名管道的最大区别。

有名管道叫named pipe或者FIFO(先进先出)，可以用函数mkfifo()创建。

* Linux管道的实现机制

在Linux中，管道是一种使用非常频繁的通信机制。从本质上说，管道也是一种文件，但它又和一般的文件有所不同，管道可以克服使用文件进行通信的两个问题，具体表现为：
> 限制管道的大小。实际上，管道是一个固定大小的缓冲区。在Linux中，该缓冲区的大小为1页，即4K字节，使得它的大小不象文件那样不加检验地增长。使用单个固定缓冲区也会带来问题，比如在写管道时可能变满，当这种情况发生时，随后对管道的write()调用将默认地被阻塞，等待某些数据被读取，以便腾出足够的空间供write()调用写。
> 读取进程也可能工作得比写进程快。当所有当前进程数据已被读取时，管道变空。当这种情况发生时，一个随后的read()调用将默认地被阻塞，等待某些数据被写入，这解决了read()调用返回文件结束的问题。
> 
*注意：从管道读数据是一次性操作，数据一旦被读，它就从管道中被抛弃，释放空间以便写更多的数据*
```
1. 管道的结构

     在 Linux 中，管道的实现并没有使用专门的数据结构，而是借助了文件系统的file结构和VFS的索引节点inode。通过将两个 file 结构指向同一个临时的 VFS 索引节点，而这个 VFS 索引节点又指向一个物理页面而实现的。

2.管道的读写

    管道实现的源代码在fs/pipe.c中，在pipe.c中有很多函数，其中有两个函数比较重要，即管道读函数pipe_read()和管道写函数pipe_wrtie()。管道写函数通过将字节复制到 VFS 索引节点指向的物理内存而写入数据，而管道读函数则通过复制物理内存中的字节而读出数据。当然，内核必须利用一定的机制同步对管道的访问，为此，内核使用了锁、等待队列和信号。

    当写进程向管道中写入时，它利用标准的库函数write()，系统根据库函数传递的文件描述符，可找到该文件的 file 结构。file 结构中指定了用来进行写操作的函数（即写入函数）地址，于是，内核调用该函数完成写操作。写入函数在向内存中写入数据之前，必须首先检查 VFS 索引节点中的信息，同时满足如下条件时，才能进行实际的内存复制工作：
 
    内存中有足够的空间可容纳所有要写入的数据；  
    内存没有被读程序锁定。  
 
如果同时满足上述条件，写入函数首先锁定内存，然后从写进程的地址空间中复制数据到内存。否则，写入进程就休眠在VFS索引节点的等待队列中，接下来，内核将调用调度程序，而调度程序会选择其他进程运行。写入进程实际处于可中断的等待状态，当内存中有足够的空间可以容纳写入数据，或内存被解锁时，读取进程会唤醒写入进程，这时，写入进程将接收到信号。当数据写入内存之后，内存被解锁，而所有休眠在索引节点的读取进程会被唤醒。

管道的读取过程和写入过程类似。但是，进程可以在没有数据或内存被锁定时立即返回错误信息，而不是阻塞该进程，这依赖于文件或管道的打开模式。反之，进程可以休眠在索引节点的等待队列中等待写入进程写入数据。当所有的进程完成了管道操作之后，管道的索引节点被丢弃，而共享数据页也被释放。
```

      
// grep



// test











