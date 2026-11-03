# Changelog

All notable changes to this template are documented here.

The format is based on [Keep a Changelog](https://keepachangelog.com/),
and this project adheres to [Semantic Versioning](https://semver.org/).

## [1.0.0] - 2026-11-03

### Added
- Initial release of the **ICMP Ping DNS** template for Zabbix 7.0.
- 8 DNS-query items that resolve the host against 4 public DNS resolvers
  (Google DNS `8.8.4.4` / `8.8.8.8` and IPv6 `2001:4860:4860::8844` / `::8888`),
  for both `A` and `AAAA` records.
- A calculated `net.dns.record.deduplicated` item that concatenates and
  de-duplicates the resolved IPs via JavaScript preprocessing.
- A dependent Low-Level Discovery rule (`discovery`) keyed on `{#IP}` from the
  JSONPath `$.ip`.
- 3 item prototypes per discovered IP: `icmpping[{#IP}]` (Up/Down),
  `icmppingloss[{#IP}]` (%), `icmppingsec[{#IP}]` (s).
- 3 trigger prototypes with dependencies (Unavailable = High, High loss &
  High latency = Warning).
- Tunable macros `{$ICMP_LOSS_WARN}` (20) and `{$ICMP_RESPONSE_TIME_WARN}` (0.15).
- `Service state` value map (0 → Down, 1 → Up).
- Tagging: `class:network`, `target:icmp`, `component:health/network`,
  `scope:availability/performance`.
- Demo host export `www.zabbix.com` (links the template) under `examples/`.
- Exports in YAML, XML and JSON (Zabbix 7.0 format).
