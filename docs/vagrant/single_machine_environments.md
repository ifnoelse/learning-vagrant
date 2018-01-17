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
- **config.vm.boot_timeout** The time in seconds that Vagrant will wait for the machine to boot and be accessible. By default this is 300 seconds.
- **config.vm.box** This configures what box the machine will be brought up against. The value here should be the name of an installed box or a shorthand name of a box in HashiCorp's Vagrant Cloud.
- This option requires Vagrant 1.5 or higher. You can download the latest version of Vagrant from the Vagrant installers page.
- **config.vm.box_check_update** If true, Vagrant will check for updates to the configured box on every vagrant up. If an update is found, Vagrant will tell the user. By default this is true. Updates will only be checked for boxes that properly support updates (boxes from HashiCorp's Vagrant Cloud or some other versioned box).
- **config.vm.box_download_checksum** The checksum of the box specified by config.vm.box_url. If not specified, no checksum comparison will be done. If specified, Vagrant will compare the checksum of the downloaded box to this value and error if they do not match. Checksum checking is only done when Vagrant must download the box.
- If this is specified, then config.vm.box_download_checksum_type must also be specified.
- **config.vm.box_url** The URL that the configured box can be found at. If config.vm.box is a shorthand to a box in HashiCorp's Vagrant Cloud then this value does not need to be specified. Otherwise, it should point to the proper place where the box can be found if it is not installed.
- This can also be an array of multiple URLs. The URLs will be tried in order. Note that any client certificates, insecure download settings, and so on will apply to all URLs in this list.
- The URLs can also be local files by using the file:// scheme. For example: "file:///tmp/test.box".
- **config.vm.box_version** The version of the box to use. This defaults to ">= 0" (the latest version available). This can contain an arbitrary list of constraints, separated by commas, such as: >= 1.0, < 1.5. When constraints are given, Vagrant will use the latest available box satisfying these constraints.
- **config.vm.hostname** The hostname the machine should have. Defaults to nil. If nil, Vagrant will not manage the hostname. If set to a string, the hostname will be set on boot.
- **config.vm.network** Configures networks on the machine. Please see the networking page for more information.
- **config.vm.provider** Configures provider-specific configuration, which is used to modify settings which are specific to a certain provider. If the provider you are configuring does not exist or is not setup on the system of the person who runs vagrant up, Vagrant will ignore this configuration block. This allows a Vagrantfile that is configured for many providers to be shared among a group of people who may not have all the same providers installed.
- **config.vm.provision** Configures provisioners on the machine, so that software can be automatically installed and configured when the machine is created. Please see the page on provisioners for more information on how this setting works.
- **config.vm.synced_folder** Configures synced folders on the machine, so that folders on your host machine can be synced to and from the guest machine. Please see the page on synced folders for more information on how this setting works.
