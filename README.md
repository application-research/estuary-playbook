# estuary-playbook
[Estuary](https://github.com/application-research/estuary) with a bit of automation magic.

## Requirements
Install the required roles using `ansible-galaxy install -r requirements.yml`.

## Preparation
First, we'll need some machines to run Estuary on. These can be virtual machines, LXC/LXD containers, or physical machines.

Modern versions of Ubuntu and Debian are supported by this playbook; support for distros such as Arch Linux and openSuSE is being considered.

* estuary-main - to run the main Estuary services
* estuary-shuttleX - one or more shuttles to store and move data to the edge of space
* estuary-www - to run the web frontend

Once the machines have been built, you'll need to generate keys and make them trusted by either root (if logging in as root) or your user.

If you'll be able to reach those machines via DNS without specifically needing to add a domain name (to turn the hostnames into FQDNs, in other words), you're now ready to go. Otherwise, edit `inventory` to suit.

## Configuration
Edit `vars/estuary-settings.yml` and adjust any settings you need to adjust.

Make sure any hostnames used in the configuration are reachable via ping or a similar tool.

Copy `vars/secrets.yml.dist` to `vars/secrets.yml`

`cp vars/secrets.yml.dist vars/secrets.yml`

Edit your new secrets.yml file and set passwords for PostgreSQL (skip this step if you're using SQLite).

## Usage
Installing Estuary:
* Run `ansible-playbook site.yml`

Upgrading Estuary:
* TODO
