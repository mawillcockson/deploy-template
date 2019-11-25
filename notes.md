get https://get.rvm.io
  creates: ~/rvm-install.sh

command: rvm-install.sh stable
  creates: ~/.rvm/

rvm list | grep ruby-2.6.1
  rvm install ruby-2.6.1

gem install bundler
cd Movementt-back && bundle install

package: npm

cd Movementt-front && npm install

caddy
  accept-eula
  email = something
  firewall:
    80
    443
  proxy to :3001
