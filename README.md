# hello-world
It's just emmmmmm

select:讲socket文件描述符放入一个fd_set，拷贝进内核空间，由内核遍历socket是否有事件发生，标记可读或可写，接着把整个fd_set拷贝回用户态，再通过遍历检查可读或可写，select用BitsMap组织文件描述符，最多存储1024个
poll：原理与select相似，但是是以动态数组存储，用链表的形式组织，没有1024的限制。
epoll:在内核中维护了一个红黑树存储待检测的socket，当有时间发生时，放入到就绪队列
