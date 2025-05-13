Vagrant.configure("2") do |config|
  # Your existing configuration here
  
  # Add these lines INSIDE the configure block
  config.vm.provision "file", source: "./VBoxGuestAdditions_7.0.26.iso", destination: "/tmp/VBoxGuestAdditions.iso"
  
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y build-essential dkms linux-headers-$(uname -r)
    mkdir -p /mnt/guestadditions
    mount -o loop /tmp/VBoxGuestAdditions.iso /mnt/guestadditions
    /mnt/guestadditions/VBoxLinuxAdditions.run
    umount /mnt/guestadditions
    rm -f /tmp/VBoxGuestAdditions.iso
  SHELL
end
