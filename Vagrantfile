Vagrant.configure("2") do |config|

  config.vm.define "zabbix" do |zabbix|
    zabbix.vm.box = "debian/jessie64"
	zabbix.vm.hostname = "zabbix-server"
	zabbis.vm.network "forwarded_port", guest: 8080, host: 8080
	zabbix.vm.provision :shell, inline: "apt install curl -y && curl -fsSL https://get.docker.com -o get-docker.sh && sudo sh ./get-docker.sh"

  end
end
