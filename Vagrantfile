# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  # MonitoRSS, use this for general testing
  # vagrant up monitorss
  config.vm.define "monitorss" do |monitorss|
    monitorss.vm.box = "debian/buster64"
    monitorss.vm.box_check_update = true
    monitorss.vm.network "forwarded_port", guest: 8081, host: 8081
    monitorss.vm.synced_folder ".", "/vagrant", disabled: true

    monitorss.vm.provision :ansible do |ansible|
      ansible.verbose = "v"
      ansible.raw_arguments = ["--connection=paramiko"]
      ansible.playbook = "monitorss.yml"
      ansible.skip_tags = "vagrant_skip"
      ansible.groups = {
        "MonitoRSS_production" => ["monitorss"]
      }
    end
  end
end
