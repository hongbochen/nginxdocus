当前，nginx包对于下列发行版和版本是可用的：

RHEL/CentOS:

| 版本 | 支持平台 |
| :--- | :--- |
| 6.x | x86\_64,i386 |
| 7.4+ | x86\_64, ppc64le |

Debian:

| 版本 | 代码名称 | 支持平台 |
| :--- | :--- | :--- |
| 8.x | jessie | x86\_64,i386 |
| 9.x | stretch | x86\_64,i386 |

Ubuntu:

| 版本 | 代码名称 | 支持平台 |
| :--- | :--- | :--- |
| 14.04 | trusty | x86\_64, i385, aarcg64/arm64 |
| 16.04 | xenial | x86\_64, i386, ppc64el, aarch64/arm64 |
| 18.04 | bionic | x86\_64,aarch64/arm64 |
| 18.10 | cosmic | x86\_64 |

SLES:

| 版本 | 支持平台 |
| :--- | :--- |
| 12 | x86\_64 |
| 15 | x86\_64 |

为了启用Linux包管理的自动更新，请rhel/centos发行版设置yum存储库，为Debian/Ubuntu发行版配置apt存储库或为SLES配置zypper存储库。

### 为稳定版本预构建包

为RHEL/CentOS设置yum存储库，创建下列内容的名称为`/etc/yum.repos.d/nginx.repo`的文件：

```
[nginx]
name=nginx repo
baseurl=http://nginx.org/packages/OS/OSRELEASE/$basearch/
gpgcheck=0
enabled=1
```



