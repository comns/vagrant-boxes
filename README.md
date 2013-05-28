# Comns Vagrant boxes
This repository includes our efforts at creating [vagrant][] boxes
using [veewee][]. Currently its only for the *vmware-fusion-provider*
(which also makes it mac only).

## Requirements
All of these are tested on *Mountain Lion*:

* [Vmware Fusion][fusion] 5.0.x
* Ruby 1.9.3 with bundler
* [Vagrant][vagrant] (currently using 1.2.2) with
  *vmware-fusion-plugin*.
  
## Development process

### Install dependencies
After installing the above requirements change directory to the root
of this project and run:

    # bundle install

### Building definition
To build a box from existing definition run:

    # bundle exec veewee fusion build <definition-name>

Existing definitions are listed below.

### Exporting boxes
To export the box run:

    # bundle exec veewee fusion export <definition-name>

Then import the resulting box to vagrant.

## Definitions

### comns-precise64
This is based on the `ubuntu-12.04.1-server-amd64` template, but omits
the ruby/chef/puppet/virtualbox scripts (why virtualbox even exists
here? must be a bug). The resulting box should be run either when
chef/puppet is not needed or with [vagrant-omnibus][].

*Note that currently only [this fork][fork] of the vagrant omnibus
plugin works with the vmware provider.*

## Resources
Some resources for creating vagrant images:

* [Blog post][blog] describing manual creating of boxes.
* [Bento][] - Opscode veewee definitions.

[vagrant]: http://vagrantup.com
[fusion]:  http://www.vmware.com/products/fusion/overview.html
[veewee]:  https://github.com/jedi4ever/veewee/
[blog]:    http://cbednarski.com/articles/creating-vagrant-base-box-for-centos-62/
[Bento]:   https://github.com/opscode/bento
[fork]:    https://github.com/rjocoleman/vagrant-omnibus
[vagrant-omnibus]: https://github.com/schisamo/vagrant-omnibus
