# 单虚拟机环境
## 定义虚拟机
- 新建一个目录，目录名任意
- 将以下内容保存到名为Vagrantfile的文件中
``` ruby
VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.define "web" do |web|
    web.vm.box = "bento/centos-7.4"
  end
end
```
- 在新建目录下执行`vagrant up`启动虚拟机

## 相关参数说明
 - **vm.box** 