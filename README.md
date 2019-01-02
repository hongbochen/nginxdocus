nginx\[engine x\]是一个HTTP和反向代理服务器，一个邮件代理服务器和一个通用的TCP/UDP代理服务器，起初是有lgor Sysoev编写。有很长一段时间，他已经运行在很多负载很重的俄罗斯网站上，其中包括Yandex, Mail.Ru 和 Rambler。通过Netcraft，nginx在2018年12月服务或代理了25.98%的最忙碌的网站。

## 基本的Http服务器特征

* 服务静态文件和索引文件，自动索引；打开文件描述符缓存；
* 使用缓存加速反向代理；负载均衡和容错
* 加速对FastCGI, uwsgi, SCGI和内存缓存服务器的缓存的支持；负载均衡和容错
* 模块化架构。过滤器包括gzipping, 字节范围，分块响应， XSLT，SSI和图片转换过滤器。在一个单一的页面中多个SSI包含可以被并行处理，如果他们是被代理或FastCGI/uwsgi/SCGI服务器处理的话；
* SSL和TSL SNI支持；
* 支持带有权重或基于依赖的有限关系的HTTP/2;

## 其他HTTP服务器特征

 - 基于命名和基于IP的虚拟服务器；

 - Keep-alive和管道连接支持



