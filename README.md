nginx\[engine x\]是一个HTTP和反向代理服务器，一个邮件代理服务器和一个通用的TCP/UDP代理服务器，起初是有lgor Sysoev编写。有很长一段时间，他已经运行在很多负载很重的俄罗斯网站上，其中包括Yandex, Mail.Ru 和 Rambler。通过Netcraft，nginx在2018年12月服务或代理了25.98%的最忙碌的网站。

## 基本的Http服务器特征

* 服务静态文件和索引文件，自动索引；打开文件描述符缓存；
* 使用缓存加速反向代理；负载均衡和容错
* 加速对FastCGI, uwsgi, SCGI和内存缓存服务器的缓存的支持；负载均衡和容错
* 模块化架构。过滤器包括gzipping, 字节范围，分块响应， XSLT，SSI和图片转换过滤器。在一个单一的页面中多个SSI包含可以被并行处理，如果他们是被代理或FastCGI/uwsgi/SCGI服务器处理的话；
* SSL和TSL SNI支持；
* 支持带有权重或基于依赖的有限关系的HTTP/2;

## 其他HTTP服务器特征

* 基于命名和基于IP的虚拟服务器；

* Keep-alive和管道连接支持；

* 访问日志格式化，缓冲日志写入，快速日志旋转和系统日志记录；

* 3xx-5xx错误代码重定向；

* 重写模块：使用正则表达式改变URI

* 依赖客户端地址运行不同的方法；

* 基于客户端IP地址，通过密码（HTTP基本认证）和通过子请求结果进行访问控制；

* HTTP引用验证；

* PUT, DELETE, MKCOL, COPY和MOVE方法；

* FLV和MP4流；

* 响应率限制；

* 限制来自同一个地址的同时连接或请求的数量；

* 基于IP的地理定位；

* A/B测试；

* 请求镜像；

* 嵌入式Perl

* njs脚本语言。

## 邮件代理服务器特征

* 使用外部HTTP验证服务器用户重定向到IMAP或POP3；

* 使用一个外部HTTP验证服务器和连接重定向到一个内部SMTP服务器进行用户验证。

* 认证方法：

  * POP3：USER/PASS, APOP, AUTH LOGIN/PLAIN/CRAM-MD5;
  * IMAP: LOGIN, AUTH LOGIN/PLAIN/CRAM-MD5;
  * SMTP: AUTH LOGIN/PLAIN/CRAM-MD5

* SSL支持；

* STARTTLS和STLS支持。

## TCP/UDP代理服务器特征

* TCP和UDP的常用代理；

* TCP的SSL和TLS SNI支持。

* 负载均衡和容错；

* 基于客户端地址的访问控制；

* 依赖客户端地址执行不同的方法；

* 限制来自同一个地址的同时连接或请求的数量；

* 访问日志格式化，缓冲日志写入，快速日志旋转和系统日志记录；

* 基于IP的地理定位；

* A/B测试；

* njs脚本语言。

## 架构和扩展性

* 一个主进程和多个工作进程；工作进行运行在一个无特权的用户下；
* 灵活的配置；
* 一个可执行文件的重新配置与更新不需要中断客户端服务；
* 支持kqueue\(Free BSD 4.1+\), epoll\(Linux 2.6+\), /dev/poll\(Solaris 7 11/99+\)，event ports\(Solaris 10\)，select和poll；
* 多个kqueue特征的支持包括EV_CLEAR, EV\_DISABLE\(暂时关闭事件\), NOTE\_LOWAT, EV_\_EOF，可用数据数量，错误码；
* 多个epoll特征的支持包括WPOLLRDHUP\(Linux 2.6.17+, glibc 2.8+\)和EPOLLEXCLUSIVE\(Linux 4.5+, glibc 2.24+\)；
* sendfile\(Free BSD 3.1+,Linux 2.2+, maxOS 10.5+\), sendfile64\(Linux 2.4.21+\)和sendfilev\(Solaris 8 7/01 +\)支持；
* File AIO\(Free BSD 4.3+, Linux 2.6.22+\)；
* DIRECTID\(FreeBSD 4.4+, Linux 2.4+, Solaris 2.6+, macOS\);
* 接收过滤器\(FreeBSD 4.1+, NetBSD 5.0+\)和TCP\_DEFER\_ACCEPT \(Linux 2.4+\)支持；
* 10000个不活跃的HTTP keep-alive连接消耗大约2.5M内存；
* 数据复制操作被保持在一个最小值。

## 测试的OS和平台

* FreeBSD 3 — 11 / i386; FreeBSD 5 — 11 / amd64;

* Linux 2.2 — 4 / i386; Linux 2.6 — 4 / amd64; Linux 3 — 4 / armv6l, armv7l, aarch64, ppc64le;

* Solaris 9 / i386, sun4u; Solaris 10 / i386, amd64, sun4v;

* AIX 7.1 / powerpc;

* HP-UX 11.31 / ia64;

* macOS / ppc, i386;

* Windows XP, Windows Server 2003.



