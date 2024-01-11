# Ansible Role: dbrennand.nextdns

Ansible role to install and configure the [NextDNS CLI](https://github.com/nextdns/nextdns).

## Requirements

None.

## Role Variables

```yaml
nextdns_state: present
```

Whether or not to remove NextDNS. Valid options are: `present`, `latest` and `absent`.

```yaml
nextdns_mode: workstation
```

The NextDNS mode to use. Valid options are: `workstation` and `router`.

```yaml
nextdns_report_client_info: true
```

Whether or not to report client information to NextDNS. This data will show in the NextDNS web interface.

```yaml
nextdns_profile_id: "abc123"
```

The NextDNS profile ID to use. This is a **mandatory** variable. The profile ID should be a 6 character alphanumeric string. You can find your profile ID in the NextDNS web interface under *Endpoints*.

```yaml
nextdns_args: "-cache-size=10MB -max-ttl=5s"
```

Additional arguments to pass to the NextDNS CLI `config set` command.

## Example Playbook

```yaml
---
- name: Install NextDNS
  hosts: all
  roles:
    - role: dbrennand.nextdns
      vars:
        nextdns_profile_id: "abc123"
        nextdns_args: "-cache-size=10MB -max-ttl=5s"
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) for details.

## Authors & Contributors

[**dbrennand**](https://github.com/dbrennand) - *Author*
