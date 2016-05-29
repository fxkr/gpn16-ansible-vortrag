Vagrant.configure(2) do |config|

  config.vm.define "demo.gpn.entropia.de" do |box|

    box.vm.box = "martin-v/debian-jessie-libvirt"
    box.vm.hostname = "demo.gpn.entropia.de"

    box.vm.provider :libvirt do |domain|
      domain.memory = 128
      domain.cpus = 1
      domain.nested = true
      domain.volume_cache = 'none'
    end

    box.vm.provision :ansible do |ansible|
      ansible.force_remote_user = true
      ansible.playbook = "site.yml"
    end

  end

end
