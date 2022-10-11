# vmware-vmmon_vmnet
fix to vmware vmmon issues

<pre>

### Install VMware Workstation pro on linux

  https://www.vmware.com/go/getworkstation-linux 
  sudo sh ~/Downloads/VMware-Workstation-Full-*

### Free VMware Workstation Pro full license keys 

  https://gist.github.com/williamgh2019/cc2ad94cc18cb930a0aab42ed8d39e6f

### linux headers issues

  sudo apt-get update
  sudo apt-get upgrade
  reboot 
  sudo apt-get install linux-headers-$(uname -r)                    # after reboot write this command
  

### fix to vmware vmmon issues

  git clone -b workstation-$(vmware --version | cut -d' ' -f3) https://github.com/mkubecek/vmware-host-modules.git

  cd vmware-host-modules/
  tar -cf vmnet.tar vmnet-only
  tar -cf vmmon.tar vmmon-only
  sudo cp -v vmmon.tar vmnet.tar /usr/lib/vmware/modules/source/
  sudo vmware-modconfig --console --install-all
  </pre>
