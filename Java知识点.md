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
原因：JVM 或者 JIT为了获得更好的性能会对语句重排序
H-B关系
在一个线程内，按照代码顺序，同个字段，书写在前面的操作先行发生于书写在后面的操作；
在多线程环境下，对一个monitor的解锁操作happens-before后续对同一个monitor的加锁操作”、“对某个volatile字段的写操作happens-before后续对同一个volatile字段的读操作</br>

<strong>Java中怎么获取一份线程 dump文件？</strong></br>
在 Linux 下，你可以通过命令 kill -3 PID （Java 进程的进程 ID）来获取 Java 应用的 dump 文件。</br>
在 Windows 下，你可以按下 Ctrl + Break来获取。这样JVM就会将线程的dump文件打印到标准输出或错误文件中，它可能打印在控制台或者日志文件中，具体位置依赖应用的配置。</br>

<strong>Java中，int类型变量的长度是一个固定值，与平台无关，都是32位。</strong></br>

<strong>Struts2 流程</strong></br>
重点关注以下几个角色：</br>
FilterDispatcher</br></br></br>
ActionMapper</br></br>
ActionProxy</br>
ConfigurationManager</br>
ActionInvocation</br>
Interceptor</br>
http请求->其它filter->FilterDispatcher，询问ActionMapper是否需要struts2处理该请求，是的话，FilterDispatcher->ActionProxy,ActionProxy访问ConfigurationManager，ConfigurationManager访问struts2.xml得到相关配置信息，ActionProxy创建ActionInvocation对象，负责action的具体执行，执行前后经过一系列的Interceptor，最后将执行的result渲染template，返回；</br>
