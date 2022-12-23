# -*- mode: ruby -*-
# vi: set ft=ruby :
$power_dns_instance = 1
$vm_ip_addr_start = 190
#$bridge = "usb0" #name of network interface with internet connection 
$bridge = "wlp2s0" #name of network interface with internet connection 
$vm_cidr = "192.168.0" # virtual machines CIDR
Vagrant.configure("2") do |config|
    config.vm.box = "generic/ubuntu2004"
    config.vm.box_check_update = false
    (1..$power_dns_instance).each do |i|
        config.vm.define "pdns-#{i}" do |node|
            node.vm.network "public_network", ip: "#{$vm_cidr}.#{$vm_ip_addr_start+i}", bridge: $bridge
            node.vm.hostname = "pdns-#{i}"
            node.vm.provider "virtualbox" do |vb|
                vb.gui = false
                vb.memory = "2048"
                vb.cpus=2
            end
        end
    end
end