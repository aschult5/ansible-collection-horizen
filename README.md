# Ansible Collection: horizen

[![Build Status](https://travis-ci.org/aschult5/ansible-collection-horizen.svg?branch=master)](https://travis-ci.org/aschult5/ansible-collection-horizen)

Configures a [Horizen](https://www.horizen.global/) secure, super, or full node on Debian/Ubuntu servers.

## Requirements

None.

## Collection Variables

See roles' variables.

	zend_port_p2p: "9033"
	firewall_allowed_tcp_ports: ["22", "{{ zend_port_p2p }}"]

Zend P2P port and the list of ports to open in firewall.

## Dependencies

See roles' dependencies.

## Example Playbook Invocation

TODO

## License

MIT

## Author Information

This role was created in 2019 by Andrew Schultz for use with [Nodeler](https://www.nodeler.com)
