Vagrant.configure("2") do |config|
  num_vms = 2
  base_ip = "192.168.56."

  (1..num_vms).each do |i|
    config.vm.define "centos-vm-#{i.to_s.rjust(2,'0')}" do |vm|
      vm.vm.box = "Centos-Template-Updated"
      vm.vm.hostname = "centos-vm-#{i.to_s.rjust(2,'0')}"

      # Static IP with unique MAC
      vm.vm.network "private_network", ip: "#{base_ip}#{100 + i}", mac: "080027#{(100+i).to_s(16).rjust(6,'0')}"

      vm.vm.provider "virtualbox" do |vb|
        vb.memory = "1024"
        vb.cpus = 1
      end
    end
  end
end
