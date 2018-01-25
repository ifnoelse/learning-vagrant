# 虚拟机网络配置

## Forwarded Ports

``` ruby
Vagrant.configure("2") do |config|
  config.vm.network "forwarded_port", guest: 80, host: 8080
end
```

## Private Networks

``` ruby
Vagrant.configure("2") do |config|
  config.vm.network "private_network", ip: "192.168.50.4"
end
```

## Public Networks

``` ruby
config.vm.network "public_network", ip: "192.168.0.17"
```