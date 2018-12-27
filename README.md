# Simple-VM-Manager
Simple VM Manager is a very simple virtualization tool written by bash.It is uses the 'chroot' function of Linux to provide a VM-like experience.Simple VM Manager allows the Guet OS share the host's Kernel ,so that it can run a "VM"  with nearly-native performance, lower resource cost and much less boot time.
# Get Started
# User Guide
Create a VM
      svm -c [your-vm-name] 
GestOS Installion
      Please note that svm does not support a normal installion of Guest OS.If you want to install a system from  LiveCD, just unpack it to /VM/your-vm-name/rootfs.You can also use kvm to install the system to a img file , then mount it on /VM/your-vm-name/rootfs or copy the guest os there.
Start a VM 
     svm -s [your-vm-name] 
Start a VM with GUI
    if you want start a VM with GUI,Xephyr is needed. Use 'svm [-g your-vm-name]  [Display Number]' to start .
    example:
    svm -g Debian :4
    Please make sure that display number is not occupied.
    You may neeed to edit the guests os's /etc/X11/xinit/xinitrc manually if the Desktop Environment failed to start.
Remove a VM
    rm /VM/your-vm-name
Remove Kernels in guest OS
     kernel in guest OS is not needed because all guest OS share the host's kernel 
     Use 'svm --clean [your-vm-name] to clean them'
