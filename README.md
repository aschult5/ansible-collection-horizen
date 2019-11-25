# Ansible Collection: horizen

[![Build Status](https://travis-ci.org/aschult5/ansible-collection-horizen.svg?branch=master)](https://travis-ci.org/aschult5/ansible-collection-horizen)

Configures a [Horizen](https://www.horizen.global/) secure, super, or full node on Debian/Ubuntu servers.

## Requirements

#### Full Nodes
None.

#### Secure Nodes
'A' DNS record resolution.
Ansible invoked with the FQDN of the target host.

#### Super Nodes
'A' DNS record resolution.
'AAAA' DNS record resolution.
Ansible invoked with the FQDN of the target host.

## Collection Variables

Pertinent variables listed below with their defaults.
See also [playbooks/vars](playbooks/vars).
See also [roles](roles) variables.
See also [dependencies'](#dependencies) variables.

	zend_port_p2p: "9033"
	firewall_allowed_tcp_ports: ["22", "{{ zend_port_p2p }}"]

Zend P2P port and the list of ports to open in firewall.
If a certificate will be generated (`certbot_create_if_missing`),
ports 80 and 443 will be added to `firewall_allowed_tcp_ports`.

	certbot_create_if_missing: false
	certbot_admin_email: email@example.com
	certbot_auto_renew: true

A valid server certificate is required for secure/super nodes.
Ansible's `inventory_hostname` is used as the FQDN for certificate generation.
Set `certbot_admin_email` to something useful if you enable `certbot_create_if_missing`.

	swap_file_path: /swapfile
	swap_file_state: present
	swap_file_size_mb: '512'

Decide whether `swap_file_path` is present or absent with `swap_file_path`.
If present, allocate `swap_file_size_mb` disk space to the file.

## Dependencies

See roles' dependencies.

- [geerlingguy.swap](https://galaxy.ansible.com/geerlingguy/swap)
- [geerlingguy.firewall](https://galaxy.ansible.com/geerlingguy/firewall)
- [geerlingguy.certbot](https://galaxy.ansible.com/geerlingguy/certbot)
- [geerlingguy.docker](https://galaxy.ansible.com/geerlingguy/docker)

## Example Playbook Invocation

TODO

## License

MIT

## Author Information

This role was created in 2019 by Andrew Schultz for use with [Nodeler](https://www.nodeler.com)
