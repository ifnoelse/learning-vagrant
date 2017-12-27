## Vagrant
## 虚拟开发环境
在项目开发中，我们经常会遇到各种各样的问题，需要使用虚拟开发环境来完成，虚拟和正式环境一样的虚拟开发环境，随着个人开发机硬件的升级，可以在本机跑虚拟机，如VMware、VirtualBox等。因此使用虚拟化开发环境，在本机可以运行自己喜欢的OS（Windows、Ubuntu、Mac等），开发的程序运行在虚拟机中，这样迁移到生产环境可以避免环境不一致导致的莫名错误。

## 什么是Vagrant
>Vagrant is a tool for building and managing virtual machine environments in a single workflow. With an easy-to-use workflow and focus on automation, Vagrant lowers development environment setup time, increases production parity, and makes the "works on my machine" excuse a relic of the past.

Vagrant的设计是为了方便的实现虚拟化环境，使用Ruby开发，基于VirtualBox、VMware等虚拟机管理软件的接口，提供了一个可配置、轻量级的便携式虚拟开发环境。使用Vagrant可以很方便的就建立起来一个虚拟环境，而且可以模拟多台虚拟机，因此可以在开发机模拟分布式系统。