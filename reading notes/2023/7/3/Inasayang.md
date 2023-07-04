使用通道实现通知

-   向一个通道发送一个值来实现单对单通知（略）

-   从一个通道接收一个值来实现单对单通知（略）

-   多对单和单对多通知（略）

-   通过关闭一个通道来实现群发通知

    -   从一个已关闭的通道可以接收到无穷个值，我们可以利用这一特性来实现群发通知

        ```
        1| ...
        2| close(ready) // 群发通知
        3| ...
        ```

        

定时通知（timer）

用通道实现自定义timer（略）



将通道用做互斥锁（mutex）

-   有两种方式将一个容量为1的缓冲通道用做互斥锁
    -   通过发送操作来加锁，通过接收操作来解锁
    -   通过接收操作来加锁，通过发送操作来解锁

这个有意思（略）



Pp. 365-371