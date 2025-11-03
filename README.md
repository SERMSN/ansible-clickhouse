# Ansible Role: clickhouse
[![License](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg)](https://opensource.org/licenses/MIT)

## Description

Deploy [Clickhouse](https://github.com/ClickHouse/ClickHouse) database system using ansible.

## Requirements

- Ansible >= 2.11 (It might work on previous versions, but we cannot guarantee it)
- Debian and python on deployer machine.

## Role Variables

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file as well as in table below.

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `clickhouse_ver` | 22.3.3.44 | Clickhouse package version. Also accepts `latest` as parameter. |
| `clickhouse_auth.user`| logger | Default user to manage clickhouse |
| `clickhouse_auth.password`| logger | Default password to manage clickhouse |

## Example

### Playbook

```yaml
---
- name: CLICKHOUSE | Install
  hosts: clickhouse
  roles:
    - role: clickhouse
      tags: clickhouse
  vars:
    - clickhouse_ver: "22.3.3.44"
    - clickhouse_auth:
      - user: "logger"
      - password: "logger"

```

## License

This project is licensed under MIT License. See [LICENSE](/LICENSE) for more details.


## Author Information

[ClickHouse](https://clickhouse.com/docs/en/index.html) by [ClickHouse, Inc.](https://clickhouse.com/company/).

Role by `InfernoFeniks`.