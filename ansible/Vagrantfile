# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  if Vagrant.has_plugin?("vagrant-proxyconf")
    config.proxy.http     = "http://cache.esiee.fr:3128/"
    config.proxy.https    = "http://cache.esiee.fr:3128/"
    config.proxy.no_proxy = "localhost,127.0.0.1,.example.com"
  end

  config.vm.define :haproxy, autostart: true do |haproxy|
    haproxy.vm.box = "centos/7"
    haproxy.vm.hostname = "haproxy"
    haproxy.vm.network "private_network", ip: "192.168.201.10"
  end

  config.vm.define :app1, autostart: true do |app1|
    app1.vm.box = "centos/7"
    app1.vm.hostname = "app1"
    app1.vm.network "private_network", ip: "192.168.201.11"
  end

  config.vm.define :app2, autostart: true do |app2|
    app2.vm.box = "centos/7"
    app2.vm.hostname = "app2"
    app2.vm.network "private_network", ip: "192.168.201.12"
  end

  config.vm.define :elasticsearch, autostart: true do |elasticsearch|
    elasticsearch.vm.box = "centos/7"
    elasticsearch.vm.hostname = "elasticsearch"
    elasticsearch.vm.network "private_network", ip: "192.168.201.13"
  end

  config.vm.define :mongodb, autostart: true do |mongodb|
    mongodb.vm.box = "centos/7"
    mongodb.vm.hostname = "mongodb"
    mongodb.vm.network "private_network", ip: "192.168.201.14"
  end

end
