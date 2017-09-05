# vagrant-envs #

This is a set of learning environments which utilize Vagrant.  Each has it's own Vagrantfile, and can be activated with ``vagrant up``.

# Troubleshooting Vagrant

## Enable gui mode

This runs the VM in normal mode (not in headless mode), so you can see the console and troubleshoot issues.  Particularly useful for network issues preventing you from SSH'ing into the VM.

```plain
network.vm.provider "virtualbox" do |v|
    v.name = "network"
    v.memory = 1024
end
```

## Conflict with NAT network

Vagrant ssh connects into the NAT network, which is always the first network interface on the vm.  If ``vagrant ssh`` isn't working, be sure you didn't setup a ``private_network`` with an IP that's in the same subnet as the NAT network which VirtualBox uses.

* See my Stackoverflow answer at the following link:

http://stackoverflow.com/a/32813981/1522091

