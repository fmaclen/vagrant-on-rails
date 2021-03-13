# vagrant-on-rails
A Vagrantfile + Provision script to install Rails 6 and common dependencies.

# What's Included
- Ubuntu 20.04 (Focal)
- rbenv 1.1.2
- Ruby 3.0.0
- PostgreSQL 12.6
- Redis 5.0.6
- NodeJS 12.13.0
- Rails 6.1.3

# Creating Rails app
During provision, a PostgreSQL user `vagrant` with `superuser` role will be created for the databases: `vagrant_test` and `vagrant_development`.
After provision is finished, enter the VM with `vagrant ssh`, it should automatically put you in the `/vagrant` directory. At this point simply run `rails new . --database=postgresql`.

To reach the Rails server from your host machine simply run `rails s -b 0.0.0.0` and point your browser to `http://192.168.55.200:3000`

<img width="1165" alt="Rails 6.1.3 / Ruby 3.0.0" src="https://user-images.githubusercontent.com/1434675/111034489-e6ec6900-83e3-11eb-93b4-949a2214524f.png">

# Things to consider
I put together the provision script based on a few others I found on GitHub and [elsewhere](https://gorails.com/setup/ubuntu/18.04).

Since I'm not super "fluent" in `bash` and `vagrant` I'm pretty sure this script can be optimized a significant amount, **if you feel like giving it a shot just do a pull request and I'll be happy to take a look at it.**

Needless to say, feel free to also remove things you don't want installed. I separated the provision script with comments so it shouldn't be hard to figure out.
