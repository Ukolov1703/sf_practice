Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-18.04"

  config.vm.network "forwarded_port", guest: 8002, host: 8002

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
    vb.cpus = 1
  end

  config.vm.provision "file", source: "~/empty_file.txt", destination: "/home/vagrant/empty_file.txt"

  config.vm.provision "shell", inline: <<-SHELL

    sudo apt-get update

    sudo apt-get install -y python3 python3-pip

    sudo pip3 install psycopg2-binary Django

    python3 --version
    pip3 --version
  SHELL
end