Vagrant.configure("2") do |config|

  config.vm.define "zabbix" do |zabbix|
    zabbix.vm.box = "debian/buster64"
	zabbix.vm.hostname = "zabbix-server"
	#zabbix.vm.network "forwarded_port", guest: 8080, host: 8080
	zabbix.vm.network "public_network", :bridge => 'Adaptador de Rede 802.11n Broadcom'
	# add swap
	zabbix.vm.provision :shell, inline: "fallocate -l 4G /swapfile && chmod 0600 /swapfile && mkswap /swapfile && swapon /swapfile && echo '/swapfile none swap sw 0 0' >> /etc/fstab"
	zabbix.vm.provision :shell, inline: "echo vm.swappiness = 10 >> /etc/sysctl.conf && echo vm.vfs_cache_pressure = 50 >> /etc/sysctl.conf && sysctl -p"
	
	# Install docker
	zabbix.vm.provision :shell, inline: "apt install curl -y && curl -fsSL https://get.docker.com -o get-docker.sh && sudo sh ./get-docker.sh"

  end
end
