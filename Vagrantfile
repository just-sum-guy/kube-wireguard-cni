nodes = [
  { :hostname => 'kube-master',  :ip => '172.10.10.11', :ram => 4096 },
  { :hostname => 'kube-node1',  :ip => '172.10.10.12', :ram => 2048 },
  { :hostname => 'kube-node2',  :ip => '172.10.10.13', :ram => 2048 },
  { :hostname => 'kube-node3',  :ip => '172.10.10.14', :ram => 2048 }
]

Vagrant.configure("2") do |config|
  nodes.each do |node|
    config.vm.define node[:hostname] do |nodeconfig|
      nodeconfig.vm.box = "bento/ubuntu-16.04";
      nodeconfig.vm.hostname = node[:hostname] + ".box"
      nodeconfig.vm.network :private_network, ip: node[:ip]
      memory = node[:ram] ? node[:ram] : 256;
      nodeconfig.vm.provider :virtualbox do |vb|
        vb.customize [
          "modifyvm", :id,
          "--memory", memory.to_s,
          "--cpus", "4"
        ]
      end
    end
  end
end
