# 单虚拟机环境
## 定义虚拟机
- 新建一个目录，目录名任意
- 将以下内容保存到名为 Vagrantfile 的文件中
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
- **config.vm.boot_timeout** The time in seconds that Vagrant will wait for the machine to boot and be accessible. By default this is 300 seconds.
- **config.vm.box** This configures what box the machine will be brought up against. The value here should be the name of an installed box or a shorthand name of a box in HashiCorp's Vagrant Cloud.
- This option requires Vagrant 1.5 or higher. You can download the latest version of Vagrant from the Vagrant installers page.
- **config.vm.box_check_update** If true, Vagrant will check for updates to the configured box on every vagrant up. If an update is found, Vagrant will tell the user. By default this is true. Updates will only be checked for boxes that properly support updates (boxes from HashiCorp's Vagrant Cloud or some other versioned box).
- If this is specified, then config.vm.box_download_checksum_type must also be specified.
- **config.vm.box_url** The URL that the configured box can be found at. If config.vm.box is a shorthand to a box in HashiCorp's Vagrant Cloud then this value does not need to be specified. Otherwise, it should point to the proper place where the box can be found if it is not installed.
- This can also be an array of multiple URLs. The URLs will be tried in order. Note that any client certificates, insecure download settings, and so on will apply to all URLs in this list.
- The URLs can also be local files by using the file:// scheme. For example: "file:///tmp/test.box".
- **config.vm.hostname** The hostname the machine should have. Defaults to nil. If nil, Vagrant will not manage the hostname. If set to a string, the hostname will be set on boot.
- **config.vm.network** Configures networks on the machine. Please see the networking page for more information.
- **config.vm.provider** Configures provider-specific configuration, which is used to modify settings which are specific to a certain provider. If the provider you are configuring does not exist or is not setup on the system of the person who runs vagrant up, Vagrant will ignore this configuration block. This allows a Vagrantfile that is configured for many providers to be shared among a group of people who may not have all the same providers installed.
- **config.vm.provision** Configures provisioners on the machine, so that software can be automatically installed and configured when the machine is created. Please see the page on provisioners for more information on how this setting works.
- **config.vm.synced_folder** Configures synced folders on the machine, so that folders on your host machine can be synced to and from the guest machine. Please see the page on synced folders for more information on how this setting works.

> 参考文档: https://www.vagrantup.com/docs/vagrantfile/machine_settings.html

## 默认 Vagrantfile 

执行以下命令，会在当前目录下生产 Vagrantfile 文件

``` bash
vagrant init bento/centos-7.4
```

具体内容如下：

``` ruby
# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = "bento/centos-7.4"

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # NOTE: This will enable public access to the opened port
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine and only allow access
  # via 127.0.0.1 to disable public access
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  # config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
  #   vb.memory = "1024"
  # end
  #
  # View the documentation for the provider you are using for more
  # information on available options.

  # Enable provisioning with a shell script. Additional provisioners such as
  # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
  # documentation for more information about their specific syntax and use.
  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL
end

```