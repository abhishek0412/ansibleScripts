# Ansible Role: MySQL

[![License](https://img.shields.io/badge/License-Apache%202.0-brightgreen.svg)](https://opensource.org/licenses/Apache-2.0)
[![Build Status](https://travis-ci.org/5KYDEV0P5/skydevops-mysql.svg?branch=master)](https://travis-ci.org/5KYDEV0P5/skydevops-mysql)

## Description

Install and configures MySQL on RedHat/CentOS and Debian/Ubuntu.

## Requirements
- Ansible >=2.4
- EPEL Repo for RedHat/Centos, which can be installed automatically using the [common](https://github.com/5KYDEV0P5/common) ansible role.



## Role Variables
All the variable that can be overridden are stored in [vars/main.yml](vars/main.yml) or [defaults/main.yml](defaults/main.yml) file as shown in the table below:

| Name                                    | Default Value   | Description                               |
|---------------------------------------- |---------------- |-----------------------------------------  |
| `mysql_user_home`                       | /root           | Default User directory                    |
| `mysql_user_name`                       | root            | Default User                              |
| `mysql_user_password`                   | root            | Default user Password                     |
| `mysql_root_home`                       | /root           | Default root User Directoty               |
| `mysql_root_username`                   | root            | root Username                             |
| `mysql_root_password`                   | root            | root user password                        |
| `mysql_user_password_update`            | no              | when 'yes' will prompt to change          |
| `mysql_enabled_on_startup`              | no              | Enable MySQL on startup                   |
| `overwrite_global_mycnf`                | yes             | Overwriting default cnf file              |
| `mysql_enablerepo`                      | ''              | MySQL repo                                |
| `mysql_port`                            | 3306            | Default mysql port                        |
| `mysql_bind_address`                    | 0.0.0.0         | Bind IP address                           |
| `mysql_skip_name_resolve`               | no              | no                                        |
| `mysql_datadir`                         | /var/lib/mysql  | Directory where mysql will be installed   |
| `mysql_sql_mode`                        | ''              |                                           |
| `mysql_log_file_group`                  | mysql           |                                           |
| `mysql_slow_query_log_enabled`          | no              | Logging slow queries                      |
| `mysql_slow_query_time`                 | 2               | slow queries time                         |
| `mysql_key_buffer_size`                 | 256M            | mysql buffer size                         |
| `mysql_max_allowed_packet`              | 64M             | Max. number of packets                    |
| `mysql_table_open_cache`                | 256             | Open cache table size                     |
| `mysql_sort_buffer_size`                | 1M              | Sort buffer size                          |
| `mysql_read_buffer_size`                | 1M              | Read buffer size                          |
| `mysql_read_rnd_buffer_size`            | 4M              | Read rnd buffer size                      |
| `mysql_myisam_sort_buffer_size`         | 64M             | Sort buffer size                          |
| `mysql_thread_cache_size`               | 8               | Thread cache                              |
| `mysql_query_cache_type`                | 0               | Query cache type                          |
| `mysql_query_cache_size`                | 16M             | Query cache size                          |
| `mysql_query_cache_limit`               | 1M              | Query cache limit                         |
| `mysql_max_connections`                 | 151             | Max number connections                    |
| `mysql_tmp_table_size`                  | 16M             | Temporary table size                      |
| `mysql_max_heap_table_size`             | 16M             | Heap table size                           |
| `mysql_group_concat_max_len`            | 1024            | concatination max length                  |
| `mysql_join_buffer_size`                | 262144          | Join buffer size                          |
| `mysql_lower_case_table_names`          | 0               | Lower case table names                    |
| `mysql_wait_timeout`                    | 28800           | timeout in msec                           |
| `mysql_event_scheduler_state`           | OFF             | State of event scheduler                  |
| `mysql_innodb_file_per_table`           | 1               | INNODB Settings                           |
| `mysql_innodb_buffer_pool_size`         | 256M            | INNODB Settings                           |
| `mysql_innodb_log_file_size`            | 64M             | INNODB Settings                           |
| `mysql_innodb_log_buffer_size`          | 8M              | INNODB Settings                           |
| `mysql_innodb_flush_log_at_trx_commit`  | 1               | INNODB Settings                           |
| `mysql_innodb_lock_wait_timeout`        | 50              | INNODB Settings                           |
| `mysql_innodb_large_prefix`             | 1               | INNODB Settings                           |
| `mysql_innodb_file_format`              | barracuda       | INNODB Settings                           |
| `mysql_mysqldump_max_allowed_packet`    | 64M             | Max Dump size allowed                     |
| `mysql_log`                             | ''              | Mysql Log                                 |
| `mysql_config_include_files`            | []              |                                           |
| `mysql_databases`                       | []              | MySQL databases                           |
| `mysql_users`                           | []              | MySQL users                               |
| `mysql_server_id`                       | 1               | MySQL ID                                  |
| `mysql_max_binlog_size`                 | 100M            | Bin Log size                              |
| `mysql_binlog_format`                   | ROW             | Log Format                                |
| `mysql_expire_logs_days`                | 10              | Log expire days                           |

## Dependencies

- Ansible [common](https://github.com/5KYDEV0P5/common) Role, to install required directory structure and packages.

## Example Playbook and defaults

### Use the following to run playbook

```yaml
- hosts: all
  become: yes
  gather_facts: yes
  roles:
    - role: 5KYDEV0P5.common

- hosts: testservers
  become: yes
  gather_facts: yes
  roles:
    - role: 5KYDEV0P5.skydevops-mysql
```

## License

- Licensed under the Apache License V2.0. 
- See the [LICENSE file](LICENSE) for details.

## Author Information

- You can find me on Twitter: [@skydevops](https://twitter.com/skydevops)
- You can find me on Facebook: [@skydevops](https://www.facebook.com/skydevops)

## Contributors

- Shashi Yebbare ([@skydevops](https://twitter.com/skydevops))