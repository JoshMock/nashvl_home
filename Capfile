require 'rubygems'
require 'railsless-deploy'   # gem install railsless-deploy


default_run_options[:pty] = true
ssh_options[:forward_agent] = true

set :user, "ubuntu"
set :use_sudo, true
set :git_shallow_clone, 1

set :domain, "nashvl.org"
set :deploy_to, "/var/www/nashvl.org"
set :current_dir, "current"

set :scm, "git"
set :repository,  "git://github.com/JoshMock/nashvl_home.git"
set :deploy_via, :remote_cache
set :scm_verbose, true
set :git_enable_submodules, 1

role :web, domain
role :app, domain


task :link_shared_directories do     
  run "ln -s #{shared_path}/photos #{release_path}/photos"
end    

after "deploy:update_code", :link_shared_directories
