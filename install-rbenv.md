sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

git clone https://github.com/rbenv/rbenv.git ~/.rbenv

cd ~/.rbenv && src/configure && make -C src

echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bash_profile
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.zshrc

~/.rbenv/bin/rbenv init

echo 'eval "$(rbenv init -)"' >> ~/.zshrc

#exit and login again
type rbenv
cd ~/.rbenv
git pull

git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build

sudo yum install -y gcc bzip2 openssl-devel libyaml-devel libffi-devel readline-devel zlib-devel gdbm-devel ncurses-devel

rbenv install -l
rbenv install 2.2.1
rbenv global 2.2.1
rbenv local 2.2.1
rbenv rehash

gem install bundler
gem env home

bundle install
#MEGA bundle

bolinha

