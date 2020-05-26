# Virtualisation avec KVM/Linux et Libvirt

## Installation avec virt-install

### Installation de Fedora

    # virt-install --name test --ram 4096 --disk path=/var/lib/libvirt/images/test.img,size=20 --vcpus 2  --os-type linux --os-variant fedora25 --network network:default --location=/home/hvad/Logiciels/Fedora-Server-netinst-x86_64-25-1.3.iso --extra-args='console=ttyS0 console=ttyS0,115200n8 serial' --nographics

### Installation de Fedora avec Kickstart

    # virt-install --name test --ram 4096 --disk path=/var/lib/libvirt/images/test.img,size=20 --vcpus 2  --os-type linux --os-variant fedora25 --network network:default --location=/home/hvad/Logiciels/Fedora-Server-netinst-x86_64-25-1.3.iso --extra-args='ks=file:/home/hvad/fedora.ks console=ttyS0 console=ttyS0,115200n8 serial' --nographics

### Installation de Centos 7 avec Kickstart

    # virt-install --name centos-gitlab --ram 1024 --disk path="/home/hvad/Machines Virtuelles/centos-gitlab.img",size=10 --vcpus 1 --os-type linux --os-variant centos7.0 --network network:default --location=/home/hvad/Logiciels/CentOS-7-x86_64-Minimal-1611.iso --extra-args='ks=http://192.168.122.146/cento7-ks.cfg console=ttyS0 console=ttyS0,115200n8 serial' --nographics 

    # virt-install --name centos7-minimal --ram 4096 --disk path=/var/lib/libvirt/images/centos7-minimal.img,size=10 --vcpus 2 --os-type linux --os-variant rhel7 --network network:default --location=/tmp/CentOS-7-x86_64-Minimal-1810.iso --initrd-inject=/tmp/ks.cfg  --extra-args='ks=file:/ks.cfg console=ttyS0 console=ttyS0,115200n8 serial' --nographics 

## Snapshot

### Créer un snapshot

    # virsh shutdown <nom_machine_virtuelle>
    # virsh snapshot-create-as --domain <nom_machine_virtuelle> --name "<nom_snapshot>"

### Liste snapshot

    # virsh snapshot-list --domain <nom_machine_virtuelle>

### Revenir à un snapshot

    # virsh shutdown <nom_machine_virtuelle>
    # virsh snapshot-revert --domain <nom_machine_virtuelle> --snapshotname <nom_snapshot>

### Supprimer un snapshot

    # virsh shutdown <nom_machine_virtuelle>
    # virsh snapshot-delete --domain <nom_machine_virtuelle> --snapshotname <nom_snapshot>

## Cloner une image

    # virt-clone --original centos7 --auto-clone

## Tips sur OSx

### Escape character is ^]
Ctrl + 6  
