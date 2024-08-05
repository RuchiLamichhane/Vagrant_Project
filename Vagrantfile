Vagrant.configure("2") do |config| 

  config.vm.define "ubuntu_vm" do |my_vm|
   config.vm.box = "ubuntu/jammy64"

   my_vm.vm.network "private_network", type: "dhcp", name: "vboxnet0" 
   my_vm.vm.hostname = "ubuntu"  
   my_vm.vm.provider "virtualbox" do |vb|   
       vb.memory = "1024"    
       vb.cpus = 1   
       vb.name = "ubuntu"  
  end  
end


config.vm.define "chatbot_vm" do |my_vm|
 config.vm.box = "ubuntu/jammy64"
  my_vm.vm.network "private_network", ip: "192.168.56.15"
  my_vm.vm.hostname = "chatbot"  
  my_vm.vm.provider "virtualbox" do |vb|   
         vb.memory = "1024"    
         vb.cpus = 1   
         vb.name = "chatbot"  
    end
 
config.vm.provision "shell", inline: <<-SHELL
    yum install -y epel-release
    yum install -y nginx
    systemctl start nginx
    systemctl enable nginx
  SHELL 
 
  end
end



