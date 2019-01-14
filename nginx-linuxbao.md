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

基于您使用的发行版本，使用"rhel"或"centos"替换"OS"，相应的，对于6.x或7.x版本，使用"6"或"7"替换"OSRELEASE"。

对于Debian/Ubuntu，为了验证nginx仓库签名和消除在nginx包的安装过程中提示关于缺少PGP键的警告，向apt程序密钥中添加一个用于验证nginx包的密钥是有必要的。在这里下载这个[密钥](http://nginx.org/keys/nginx_signing.key)：使用下面的命令添加密钥：

```
sudo apt-key add nginx_signing.key
```

对于Debian系统，使用Debian发行版代码名称替换代码名称，将下列内容添加到`/etc/apt/sources.list`文件中：

```
deb http://nginx.org/packages/debian/ codename nginx
deb-src http://nginx.org/packages/debian/ codename nginx
```

对于Ubuntu系统，使用Ubuntu发行版本的代码名称替换`codename`，并且将下列内容添加到文件`/etc/apt/sources.list`中：

```
deb http://nginx.org/packages/ubuntu/ codename nginx
deb-src http://nginx.org/packages/ubuntu/ codename nginx
```

对于Debian/Ubuntu系统，运行下面的命令：

```
apt-get update
apt-get install nginx
```

对于SLES 12，运行下面的命令：

```
zypper addrepo -G -t yum -c 'http://nginx.org/packages/sles/12' nginx
```

对于SLES 15，运行下面的命令：

```
zypper addrepo -G -t yum -c 'http://nginx.org/packages/sles/15' nginx
```

### 为主线程序预构建包

为了在RHEL/CentOS系统中，设置yum仓库，创建名称为`/etc/yum.repos.d/nginx.repo`，内容为下列内容的文件：

```
[nginx]
name=nginx repo
baseurl=http://nginx.org/packages/mainline/OS/OSRELEASE/$basearch/
gpgcheck=0
enabled=1
```

基于您使用的发行版本，使用"rhel"或"centos"替换"OS"，相应的，对于6.x或7.x版本，使用"6"或"7"替换"OSRELEASE"。

对于Debian/Ubuntu，为了验证nginx仓库签名和消除在nginx包的安装过程中提示关于缺少PGP键的警告，向apt程序密钥中添加一个用于验证nginx包的密钥是有必要的。在这里下载这个[密钥](http://nginx.org/keys/nginx_signing.key)：使用下面的命令添加密钥：

```
sudo apt-key add nginx_signing.key
```

对于Debian系统，使用Debian发行版代码名称替换代码名称，将下列内容添加到`/etc/apt/sources.list`文件中：

```
deb http://nginx.org/mainline/debian/ codename nginx
deb-src http://nginx.org/mainline/debian/ codename nginx
```

对于Ubuntu系统，使用Ubuntu发行版本的代码名称替换`codename`，并且将下列内容添加到文件`/etc/apt/sources.list`中：

```
deb http://nginx.org/mainline/ubuntu/ codename nginx
deb-src http://nginx.org/mainline/ubuntu/ codename nginx
```

对于Debian/Ubuntu系统，运行下面的命令：

```
apt-get update
apt-get install nginx
```

对于SLES 12，运行下面的命令：

```
zypper addrepo -G -t yum -c 'http://nginx.org/mainline/sles/12' nginx
```

对于SLES 15，运行下面的命令：

```
zypper addrepo -G -t yum -c 'http://nginx.org/mainline/sles/15' nginx
```



































































































































































