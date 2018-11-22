# Linux I/O模型

#### Blocking I/O

![](D:\wlf\typora_pic\1593755892-55c466c2b5fc5_articlex.png)

> 解释：
>
>

---

#### NonBlocking I/O



+ select

  ```c
  int select(int maxfdp1,fd_set *readset,fd_set *writeset,fd_set *exceptset,const struct timeval *timeout)
  ```



  > 1. fd_set拷贝: 从用户空间拷贝到内核空间
  > 2. fd_set遍历： 内核会遍历传入的fd_set，fd数量多时开销较大
  > 3. 调用后，process阻塞
  > 4. 最多1024个fd

+ poll

+ epoll

---

#### IO multiplexing

---

#### Asynchronous I/O

---

#### Signal Driven I/O

