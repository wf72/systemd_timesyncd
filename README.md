![.github/workflows/main.yml](https://github.com/wf72/systemd_timesyncd/actions/workflows/.github/workflows/main.yml/badge.svg)
# systemd_timesyncd

Ansilbe role sets the timezone and configures and enables systemd-timesyncd.

Based on role [stuvusit.systemd-timesyncd](https://github.com/stuvusIT/systemd-timesyncd)

## Requirements

OS:
- debian:
  - 10
  - 11
- ubuntu:
  - 20.04
  - 22.04

## Role Variables

| Name                               |   Default/Required    | Description                                                                       |
| ---------------------------------- | :-------------------: | --------------------------------------------------------------------------------- |
| `timesync_timezone`                |       `Etc/UTC`       | Timezone to set (relative to `/usr/share/zoneinfo`)                               |
| `timesync_ntp_hosts`               |                       | Array of NTP hosts                                                                |
| `timesync_fallback_ntp_hosts`      | `{0..3}.pool.ntp.org` | Array of fallback NTP hosts                                                       |
| `timesync_write_hwclock_on_change` |        `false`         | Whether to write the time to the hardware clock after changing the configuration. |

## Dependencies

None

## Example Playbook

```yml
- hosts: all
  roles:
  - wf72.systemd_timesyncd
    vars:
      timesync_timezone: Europe/Moscow
      timesync_ntp_hosts:
        - some.ntp.host
        - another.ntp.host
```

## License

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/).

## Author Information

- [Andrey Dorofeev](https://github.com/wf72)
