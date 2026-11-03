# Contributing to ICMP Ping DNS

Thanks for wanting to improve this template! 🎉

## Reporting issues
- Open a GitHub Issue with: Zabbix version, the template version, the host
  configuration, and the resolved IPs you expected vs. what you got.
- Include the output of `Monitoring → Latest data` for the host if possible.

## Improving the template
1. Import the template into a **test** Zabbix 7.0 instance.
2. Make your changes in the UI, then **export** it again as YAML/XML/JSON.
3. Update **all three** formats in `templates/` so they stay in sync
   (YAML is the canonical one).
4. If you changed behaviour, update `docs/implementation.md` and/or
   `docs/usage.md`, and add a line to `CHANGELOG.md` under `Unreleased`.
5. Open a Pull Request describing the *why* and the *what*.

## Ideas on the table
- IPv6-only / IPv4-only mode via macros.
- Allow the list of DNS resolvers to be configured through a macro instead of
  being hard-coded.
- A companion Grafana dashboard JSON.
- A "DNS resolution changed" trigger (detect when the set of IPs changes).

## Code of conduct
Be kind, assume good intent, and keep the template importable on a clean
Zabbix 7.0 install.
