# -*- mode: ruby -*-
# vi: set ft=ruby :

BOXES = {
  ie6: 'http://aka.ms/vagrant-xp-ie6',
  ie8: 'http://aka.ms/vagrant-xp-ie8',
  ie9: 'http://aka.ms/vagrant-win7-ie9',
  ie10: 'http://aka.ms/vagrant-win7-ie10',
  ie11: 'http://aka.ms/vagrant-win7-ie11'
}
PRIMARY = :ie10
MEMORY = (2*1024).to_s

Vagrant.configure(2) do |config|

  def setup_box(config, url)
    config.vm.box = url

    config.vm.provider "virtualbox" do |vb|
      vb.gui = true
      vb.memory = MEMORY
    end
  end

  BOXES.each do |name, url|
    options = {
      primary: (name == PRIMARY),
      autostart: (name == PRIMARY)
    }

    config.vm.define name, options do
      setup_box(config, url)
    end
  end

end
