# 快速体验
## 使用默认配置启动虚拟机
``` bash
mkdir centos
cd centos
vagrant init bento/centos-7.4
vagrant up
```
>如果本地没有bento/centos-7.4这个box，vagrant会自动从远程仓库下载

执行效果如下：
![](../img/vagrant_quickstart.png)
## 登陆虚拟机
### 关于内置用户
- 默认通过vagrnat创建的虚拟机都内置了用户名：vagrant，密码：vagrant的用户
- 一般情况下root账户的密码也是vagrant
### 通过vagrant账户登陆
执行以下命令即可登陆通过vagrant账户登陆
``` bash
vagrant ssh
```