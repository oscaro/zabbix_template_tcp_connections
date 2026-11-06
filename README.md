# zabbix_template_tcp

Zabbix templates for collecting metrics about Unix TCP connections

## Description
This is merely an English translation of [tanrakukairo's work](https://github.com/tanrakukairo/zabbix_template_tcp_connections),
with updated templates for recent versions of Zabbix.

Metrics are collected from `/proc/net/tcp` & `/proc/net/tcp6` and exported
as JSON. There is therefore no need to install specific tool, as the script
only uses standard text utils (bash, grep, awk, sed, sort, uniq).

## Installation
Move `userparameter_tcp.conf` into Zabbix agent included directory (usually
`/etc/zabbix/zabbix_agentd.d` or `/usr/local/etc/zabbix_agentd.conf.d`).

Move `json_item_tcp.sh` into `/usr/local/bin`.

Restart Zabbix agent.

Import the template into Zabbix server.

## References
- [RFC 9293 - Transmission Control Protocol (TCP) / 3.3.2. State Machine Overview](https://datatracker.ietf.org/doc/html/rfc9293#name-state-machine-overview)
- [Linux Networking Documentation / The proc/net/tcp and proc/net/tcp6 variables](https://www.kernel.org/doc/html/v5.18/networking/proc_net_tcp.html)
- [Linux System Administrator's Manual / netstat(8)](https://man7.org/linux/man-pages/man8/netstat.8.html#OUTPUT)
