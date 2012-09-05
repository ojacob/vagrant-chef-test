Vagrant::Config.run do |config|
  config.vm.box = "precise64"

  config.vm.forward_port 80, 8080
  config.vm.forward_port 22, 2222

  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = "cookbooks"
    # chef.log_level = "debug"
    chef.add_recipe "java"
    chef.json = {  
      :java => {
        :install_flavor => "oracle",
        #:remove_deprecated_packages => true,
        :jdk_version => "7",
        :jdk => {
          :"7" => {
            :x86_64 => {
              :url => "http://dl.dropbox.com/u/481876/jdk-7u7-linux-x64.tar.gz"
            }
          }
        }
      }
    }
  end
end
