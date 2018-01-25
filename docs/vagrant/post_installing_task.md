# 安装之后的任务

``` ruby
VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.define "web" do |web|
    web.vm.box = "bento/centos-7.4"
  end
  config.vm.provision "shell", inline: <<-SHELL
    yum remove docker docker-common docker-selinux docker-engine
    yum install -y yum-utils device-mapper-persistent-data lvm2
    yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
    yum install docker-ce
    echo '{"registry-mirrors": ["https://d6at4uvr.mirror.aliyuncs.com"]}'> /etc/docker/daemon.json
    systemctl daemon-reload
    systemctl restart docker
  SHELL
end
```

> https://www.vagrantup.com/docs/provisioning/shell.html