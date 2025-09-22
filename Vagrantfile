Vagrant.configure("2") do |config|
  num_vms = 2
  base_ip = "192.168.88."  # VirtualBox default host-only subnet

  (1..num_vms).each do |i|
    config.vm.define "centos-vm-#{i.to_s.rjust(2,'0')}" do |vm|
      vm.vm.box = "Centos-Template"
      vm.vm.hostname = "centos-vm-#{i.to_s.rjust(2,'0')}"
      vm.vm.network "private_network", ip: "#{base_ip}#{100 + i}"
      vm.vm.provider "virtualbox" do |vb|
        vb.memory = "1024"
        vb.cpus = 1
      end
    end
  end
end
