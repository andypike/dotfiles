require "rake"
require "fileutils"

task :default => %(install)

task :install do
  puts "Installing dotfiles..."

  backup
  create_symlinks
  install_vim_plug
end

def backup
  puts "Backing up files..."

  Dir.mkdir(backup_path) unless Dir.exist?(backup_path)

  symlinks.each do |symlink|
    file        = File.basename(symlink, ".symlink")
    backup_file = "#{backup_path}/.#{file}"
    config_file = "#{home}/.#{file}"

    FileUtils.rm(backup_file) if File.exist?(backup_file)
    FileUtils.mv(config_file, backup_file) if File.exist?(config_file)
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
  sh("vim +PlugInstall +PlugClean +qall")
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
