Vagrant.configure("2") do |config|
  config.vm.box = "generic/rocky9"

  # Define the Server
  config.vm.define "server" do |server|
    server.vm.hostname = "server"
    server.vm.network "private_network", ip: "192.168.56.10"

    # Native Vagrant 2.4+ / modern provider syntax to add a clean secondary raw disk
    server.vm.disk :disk, size: "10GB", name: "server_extra_disk"

    # Provision server-side NFS and storage tools automatically
    server.vm.provision "shell", inline: <<-SHELL
      echo "=== Configuring Server-side NFS & Storage Tools ==="
      dnf install -y nfs-utils lvm2
      
      mkdir -p /exports/labshare
      chmod 777 /exports/labshare
      echo "/exports/labshare 192.168.56.0/24(rw,sync,no_root_squash)" > /etc/exports
      
      systemctl enable --now nfs-server
      exportfs -ra
    SHELL
  end

  # Define the Client
  config.vm.define "client" do |client|
    client.vm.hostname = "client"
    client.vm.network "private_network", ip: "192.168.56.11"
    
    # Pre-install AutoFS and NFS client utilities
    client.vm.provision "shell", inline: <<-SHELL
      echo "=== Installing Client AutoFS & NFS Utilities ==="
      dnf install -y nfs-utils autofs
    SHELL
  end
end
