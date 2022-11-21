
Vagrant.configure("2") do |config|
  config.vm.define "testvm" do |node|
      node.vm.box = "bento/ubuntu-20.04-arm64"
      node.vm.hostname = "testvm"
      # Bridged network
      node.vm.network "private_network", ip:"192.168.58.112"
      # node.vm.network "public_network", ip:"192.168.58.113"
      node.vm.network "forwarded_port", id: "ssh", guest: 22, host: 2222, host_ip:"192.168.58.112"

      node.ssh.insert_key = false
      # Provider-specific configuration
      node.vm.provider "parallels" do |vb|
          # Customize the amount of memory on the VM
          vb.memory = "1024"
      end
  end
end

