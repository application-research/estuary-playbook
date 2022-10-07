# estuary-playbook
Estuary with a bit of automation magic.

## Requirements
None.

## Preparation
First, we'll need some machines to run Estuary on. These can be virtual machines, LXC/LXD containers, or physical machines.

* estuary-main (Debian or Ubuntu) - to run the main Estuary services
* estuary-shuttleX (Debian, Ubuntu or Arch Linux) - one or more shuttles to store and move data to the edge of space
* estuary-www (Debian or Ubuntu) - to run the web frontend

Once the machines have been built, you'll need to generate keys and make them trusted by either root (if logging in as root) or your user.

If you'll be able to reach those machines via DNS without specifically needing to add a domain name (to turn the hostnames into FQDNs, in other words), you're now ready to go. Otherwise, edit `inventory` to suit.

## Usage
Installing Estuary:
* Run `ansible-playbook site.yml`

Upgrading Estuary:
* TODO