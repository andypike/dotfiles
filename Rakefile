require "rake"
require "fileutils"

task :default => %(install)

task :install do
  puts "Installing dotfiles..."

  backup
  install_vim_plug
  create_symlinks
end

def backup
  puts "Backing up files..."

  Dir.mkdir(backup_path) unless Dir.exist?(backup_path)

  symlinks.each do |symlink|
    file = File.basename(symlink, ".symlink")
    FileUtils.rm("#{backup_path}/.#{file}")
    FileUtils.mv("#{home}/.#{file}", "#{backup_path}/.#{file}")
  end 
end

def create_symlinks
  puts "Creating symlinks..."

  symlinks.each do |symlink|
    file = File.basename(symlink, ".symlink")
    File.symlink("#{Dir.pwd}/#{symlink}", "#{home}/.#{file}") 
  end
end

def install_vim_plug
  puts "Installing vim-plug..."

  sh("curl -fLo #{home}/.vim/autoload/plug.vim --create-dirs http://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim")
end

def symlinks 
  Dir.glob("*.symlink")
end

def home
  ENV['HOME']
end

def backup_path
  "#{home}/.backup_dotfiles"
end
