#This implementations is under testing.

commands to run:

# ARCH
sudo pacman -S qemu libvirt dnsmasq virt-manager bridge-utils flex bison iptables-nft edk2-ovmf

# UBUNTU DEBIAN
sudo apt install qemu qemu-kvm libvirt-clients libvirt-daemon-system bridge-utils virt-manager

# CENTOS RHEL FEDORA
sudo yum install libvirt qemu-kvm

sudo systemctl enable --now libvirtd
sudo systemctl enable --now virtlogd

echo 1 | sudo tee /sys/module/kvm/parameters/ignore_msrs

sudo modprobe kvm

#To run with password:
´docker run -it \
    --device /dev/kvm \
    -e EXTRA="-display none -vnc 0.0.0.0:99,password=on" \
    -p 5555:5555 \
    -p 5999:5999 \
    sickcodes/dock-droid:latest´

#To run without password:
docker run -it \
    --device /dev/kvm \
    -v /tmp/.X11-unix:/tmp/.X11-unix \
    -e "DISPLAY=${DISPLAY:-:0.0}" \
    -p 5555:5555 \
    sickcodes/dock-droid:latest

## To more info:
#https://github.com/sickcodes/dock-droid
