# -*- mode: ruby -*-
# vim: set ft=ruby

MACHINES = {

:haproxy1 => {
        :box_name => "tulamelkii/VDebian12",
        :box_version => "12.2.7",
        :vm_name => "haproxy1",
        :vm_mem => 1024,
        :cpu => 1,
        :net => [
          {ip: '192.168.2.2', adapter: 2, netmask: "255.255.255.240"},
          {ip: '192.168.56.10', adapter: 4},

                ]
 },

:haproxy2 => {
        :box_name => "tulamelkii/VDebian12",
        :box_version => "12.2.7",
        :vm_mem => 1024,
        :vm_name => "haproxy2",
        :cpu => 1,
        :net => [
          {ip: '192.168.2.3', adapter: 2, netmask: "255.255.255.240"},
          {ip: '192.168.56.11', adapter: 4},

                ]
 },

:node1 => {
        :box_name => "tulamelkii/VDebian12",
        :box_version => "12.2.7",
        :vm_name => "node1",
        :cpu => 1,
        :vm_mem => 2500,
        :net => [
          {ip: '192.168.2.5', adapter: 2, netmask: "255.255.255.240"},
          {ip: '192.168.56.12', adapter: 4},

                ]
 },

:node2 => {
        :box_name => "tulamelkii/VDebian12",
        :box_version => "12.2.7",
        :vm_name => "node2",
        :vm_mem => 2500,
        :cpu => 1,
        :net => [
          {ip: '192.168.2.6', adapter: 2, netmask: "255.255.255.240"},
          {ip: '192.168.56.13', adapter: 4},

                ]
 },

:node3 => {
        :box_name => "tulamelkii/VDebian12",
        :box_version => "12.2.7",
        :vm_name => "node3",
        :vm_mem => 2500,
        :cpu => 1,
        :net => [
          {ip: '192.168.2.7', adapter: 2, netmask: "255.255.255.240"},
          {ip: '192.168.56.14', adapter: 4},

                ]
 },

:elk => {
        :box_name => "tulamelkii/VDebian12",
        :box_version => "12.2.7",
        :vm_mem => 7000,
        :vm_name => "elk",
        :cpu => 2,
        :net => [
          {ip: '192.168.2.8', adapter: 2, netmask: "255.255.255.240"},
          {ip: '192.168.56.15', adapter: 4},

                ]
 },

:prom => {
        :box_name => "tulamelkii/VDebian12",
        :box_version => "12.2.7",
        :vm_name => "prom",
        :cpu => 1,
        :vm_mem => 2024,
        :net => [
          {ip: '192.168.2.9', adapter: 2, netmask: "255.255.255.240"},
          {ip: '192.168.56.16', adapter: 4},

                ]
 },

:bacula => {
        :box_name => "tulamelkii/VDebian12",
        :box_version => "12.2.7",
        :vm_name => "bacula",
        :cpu => 1,
        :vm_mem => 2024,
        :net => [
          {ip: '192.168.2.10', adapter: 2, netmask: "255.255.255.240"},
          {ip: '192.168.56.17', adapter: 4},

                ]
 },


}
Vagrant.configure("2") do |config|

  MACHINES.each do |boxname, boxconfig|
    
    config.vm.define boxname do |box|
   
      box.vm.box = boxconfig[:box_name]
      box.vm.host_name = boxconfig[:vm_name]
      box.vm.box_version = boxconfig[:box_version]
      boxconfig[:net].each do |ipconf|
      box.vm.network "private_network", ip: ipconf[:ip], virtualbox__intnet: ipconf[:virtualbox__intnet], netmask: ipconf[:netmask], adapter: ipconf[:adapter]
      end
       box.vm.provider :virtualbox do |v|
        v.memory = boxconfig[:vm_mem]
        v.cpus = boxconfig[:cpu]
        v.customize ['modifyvm', :id, '--nested-hw-virt', 'on']
        v.customize ["modifyvm", :id, "--vram", "128"]        
        v.customize ["modifyvm", :id, "--accelerate3d", "on"]
      end

  
 if boxconfig[:vm_name] == "bacula"
       box.vm.provision "ansible" do |ansible|
        ansible.playbook = "maim.yml"
        ansible.inventory_path = "host"
        ansible.host_key_checking = "false"
        ansible.limit = "all"
         end
       end
    end
  end
end
