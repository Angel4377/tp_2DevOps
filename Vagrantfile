Vagrant.configure("2") do |config|

  # =======================
  # VM Application : srv-app
  # =======================
  config.vm.define "srv-app" do |srv_app|
    srv_app.vm.box = "ubuntu/jammy64"
    srv_app.vm.box_check_update = false

    srv_app.vm.network "forwarded_port", guest: 8080, host: 8081
    srv_app.vm.network "private_network", ip: "192.168.56.11"

    # Synchroniser le projet Maven avec la VM
    srv_app.vm.synced_folder "C:/Users/DELL/IdeaProjects/api_jee_diti4_2025", "/home/vagrant/project"

    srv_app.vm.provider "virtualbox" do |vb|
      vb.gui = false
      vb.name = "srv-app"
      vb.cpus = 2
      vb.memory = 1024
    end
  end

  # =======================
  # VM Database : srv-db
  # =======================
  config.vm.define "srv-db" do |srv_db|
    srv_db.vm.box = "ubuntu/jammy64"
    srv_db.vm.box_check_update = false

    srv_db.vm.network "private_network", ip: "192.168.56.12"

    srv_db.vm.provider "virtualbox" do |vb|
      vb.gui = false
      vb.name = "srv-db"
      vb.cpus = 2
      vb.memory = 1024
    end
  end

end
