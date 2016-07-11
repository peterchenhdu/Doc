<strong>Java IO</strong></br>
包括字节流和字符流</br>
主要用于读写操作，一般按用途来区分</br>
一类是干正事的，比如往媒介写入字符/字节，或往媒介读取字符/字节，这里的媒介可以是文件、字符/字节数组、管道（用于线程间通信）</br>
另一类则用于装饰其它流，如BufferedXXXX、PrintXXXX、FilterXXXX等，增加缓冲、格式化输出、过滤等功能；</br>
<strong>volatile关键字</strong></br>
1、内存可见性</br>
2、修饰64位宽的long和double变量，使之能够原子读写操作</br>
3、内存栅栏，被volatile修饰的变量在多线程环境中存在happen-before关系，写操作happens-before后续对同一个volatile字段的读操作</br>
<strong>内存栅栏</strong></br>
在一个线程内，按照代码顺序，同个字段，书写在前面的操作先行发生于书写在后面的操作；
在多线程环境下，对一个monitor的解锁操作happens-before后续对同一个monitor的加锁操作”、“对某个volatile字段的写操作happens-before后续对同一个volatile字段的读操作</br>
