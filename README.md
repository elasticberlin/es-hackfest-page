Elasticsearch Hackfest - Berlin
================

Small website to host information for the upcoming elasticsearch hackfest in berlin.

[http://shrink0r.github.io/es-hackfest-page](http://shrink0r.github.io/es-hackfest-page)

## Development

You may either develop locally or you can use the provided vagrant setup.

### Developing with vagrant

#### Requirements

* [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
* [VirtualBox Extension Pack](http://www.oracle.com/technetwork/server-storage/virtualbox/downloads/index.html#extpack)
* [Vagrant](http://downloads.vagrantup.com/)
* vagrant-vbguest - ```vagrant plugin install vagrant-vbguest```

#### Setup

Clone repository  
```git clone git@github.com:shrink0r/es-hackfest-page.git```

Boot and provision vagrant box
```cd es-hackfest-page/dev/vagrant```  
```vagrant up --provision```

Ssh into dev box and setup project  
```vagrant ssh```  
```cd projects```  
```git clone git@github.com:shrink0r/es-hackfest-page.git```  
```cd es-hackfest-page/app```

An nfs share is provided under ```nfs://es-hackfest-page.local/home/vagrant/projects/```  
The site itself is hosted at [http://es-hackfest-page.local](http://es-hackfest-page.local).  
In order to deploy changes to the site during development call ```make``` inside the app directory.

### Developing locally

#### Requirements

* [jekyll](http://jekyllrb.com/) - ```gem install jekyll```
* [sass](http://sass-lang.com/install) - ```gem install sass```
* [nokogiri](https://rubygems.org/gems/nokogiri) - ```gem install nokogiri```
* [rdiscount](https://rubygems.org/gems/rdiscount) - ```gem install rdiscount```

#### Setup

Clone repository  
```git clone git@github.com:shrink0r/es-hackfest-page.git```  
```cd es-hackfest-page/app```

After making changes to the site, you must deploy by calling: ```make```.

## Deploying changes

When you have finished making changes to the site and want to publish them call ```make deploy```.
Then copy and commit the pub directory's contents to the gh-pages branch.
