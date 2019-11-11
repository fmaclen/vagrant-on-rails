# vagrant-on-rails
A Vagrantfile + Provision script to install Rails 6 and common dependencies.

# What's Included
- Ubuntu 18.04.3 LTS (Bionic Beaver)
- rbenv 1.1.2
- Ruby 2.6.5
- PostgreSQL 9.x
- Redis 5.0.6
- NodeJS 12.13.0
- Yarn 1.19.1
- Rails 6.0.1

# Creating Rails app
During provision, a PostgreSQL user `vagrant` with `superuser` role will be created for the databases: `vagrant_test` and `vagrant_development`. 
After provision is finished, enter the VM with `vagrant ssh`, it should automatically put you in the `/vagrant` directory. At this point simply run `rails new . --database=postgresql`.

To reach the Rails server from your host machine simply run `rails s -b 0.0.0.0` and point your browser to `http://192.168.55.200:3000`

# Things to consider
I put together the provision script based on a few others I found on GitHub and [elsewhere](https://gorails.com/setup/ubuntu/18.04).

Since I'm not super "fluent" in `bash` and `vagrant` I'm pretty sure this script can be optimized a significant amount, **if you feel like giving it a shot just do a pull request and I'll be happy to take a look at it.**

Needless to say, feel free to also remove things you don't want installed. I separated the provision script with comments so it shouldn't be hard to figure out.

Finally, this pretty much works out of the box on **Mac OS** but I had some issues installing `yarn` and `webpacker` under **Windows**, the issue is related to the creation of symlinks. Apparently the way to "fix" that is to run your terminal app as an *Administrator*, but at the time of this commit I haven't had time to properly test it.
