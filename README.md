influxdb
========

[![Build Status](https://travis-ci.org/kbrebanov/ansible-influxdb.svg?branch=master)](https://travis-ci.org/kbrebanov/ansible-influxdb)

Installs and configures InfluxDB.

Requirements
------------

This role requires Ansible 1.9 or higher.

Role Variables
--------------

| Name                                             | Default                      | Description |
|:-------------------------------------------------|:-----------------------------|:------------|
| influxdb_version                                 | 0.13                         |             |
| influxdb_reporting_disabled                      | false                        |             |
| influxdb_meta_dir                                | /var/lib/influxdb/meta       |             |
| influxdb_meta_retention_autocreate               | true                         |             |
| influxdb_meta_logging_enabled                    | true                         |             |
| influxdb_meta_pprof_enabled                      | false                        |             |
| influxdb_meta_lease_duration                     | 1m0s                         |             |
| influxdb_data_dir                                | /var/lib/influxdb/data       |             |
| influxdb_data_engine                             | tsm1                         |             |
| influxdb_data_wal_dir                            | /var/lib/influxdb/wal        |             |
| influxdb_data_wal_logging_enabled                | true                         |             |
| influxdb_data_query_log_enabled                  | true                         |             |
| influxdb_data_cache_max_memory_size              | 524288000                    |             |
| influxdb_data_cache_snapshot_memory_size         | 26214400                     |             |
| influxdb_data_cache_snapshot_write_cold_duration | 1h0m0s                       |             |
| influxdb_data_compact_full_write_cold_duration   | 24h0m0s                      |             |
| influxdb_data_max_points_per_block               | 0                            |             |
| influxdb_data_logging_enabled                    | true                         |             |
| influxdb_cluster_force_remote_mapping            | false                        |             |
| influxdb_cluster_write_timeout                   | 10s                          |             |
| influxdb_cluster_shard_writer_timeout            | 5s                           |             |
| influxdb_cluster_max_remote_write_connections    | 3                            |             |
| influxdb_cluster_shard_mapper_timeout            | 5s                           |             |
| influxdb_cluster_max_concurrent_queries          | 0                            |             |
| influxdb_cluster_query_timeout                   | 0                            |             |
| influxdb_cluster_log_queries_after               | 0                            |             |
| influxdb_cluster_max_select_point                | 0                            |             |
| influxdb_cluster_max_select_series               | 0                            |             |
| influxdb_cluster_max_select_buckets              | 0                            |             |
| influxdb_retention_enabled                       | true                         |             |
| influxdb_retention_check_interval                | 30m0s                        |             |
| influxdb_shard_precreation_enabled               | true                         |             |
| influxdb_shard_precreation_check_interval        | 10m0s                        |             |
| influxdb_shard_precreation_advance_period        | 30m0s                        |             |
| influxdb_admin_enabled                           | true                         |             |
| influxdb_admin_bind_address                      | ":8083"                      |             |
| influxdb_admin_https_enabled                     | false                        |             |
| influxdb_admin_https_certificate                 | /etc/ssl/influxdb.pem        |             |
| influxdb_monitor_store_enabled                   | true                         |             |
| influxdb_monitor_store_database                  | _internal                    |             |
| influxdb_monitor_store_interval                  | 10s                          |             |
| influxdb_subscriber_enabled                      | true                         |             |
| influxdb_http_enabled                            | true                         |             |
| influxdb_http_bind_address                       | ":8086"                      |             |
| influxdb_http_auth_enabled                       | false                        |             |
| influxdb_http_log_enabled                        | true                         |             |
| influxdb_http_write_tracing                      | false                        |             |
| influxdb_http_pprof_enabled                      | false                        |             |
| influxdb_http_https_enabled                      | false                        |             |
| influxdb_http_https_certificate                  | /etc/ssl/influxdb.pem        |             |
| influxdb_http_max_row_limit                      | 10000                        |             |
| influxdb_graphite_enabled                        | false                        |             |
| influxdb_graphite_bind_address                   | ":2003"                      |             |
| influxdb_graphite_database                       | graphite                     |             |
| influxdb_graphite_protocol                       | tcp                          |             |
| influxdb_graphite_batch_size                     | 5000                         |             |
| influxdb_graphite_batch_pending                  | 10                           |             |
| influxdb_graphite_batch_timeout                  | 1s                           |             |
| influxdb_graphite_consistency_level              | one                          |             |
| influxdb_graphite_separator                      | .                            |             |
| influxdb_graphite_udp_read_buffer                | 0                            |             |
| influxdb_collectd_enabled                        | false                        |             |
| influxdb_collectd_bind_address                   | ":25826"                     |             |
| influxdb_collectd_database                       | collectd                     |             |
| influxdb_collectd_batch_size                     | 5000                         |             |
| influxdb_collectd_batch_pending                  | 10                           |             |
| influxdb_collectd_batch_timeout                  | 10s                          |             |
| influxdb_collectd_read_buffer                    | 0                            |             |
| influxdb_collectd_typesdb                        | /usr/share/collectd/types.db |             |
| influxdb_opentsdb_enabled                        | false                        |             |
| influxdb_opentsdb_bind_address                   | ":4242"                      |             |
| influxdb_opentsdb_database                       | opentsdb                     |             |
| influxdb_opentsdb_retention_policy               | ''                           |             |
| influxdb_opentsdb_consistency_level              | one                          |             |
| influxdb_opentsdb_tls_enabled                    | false                        |             |
| influxdb_opentsdb_certificate                    | /etc/ssl/influxdb.pem        |             |
| influxdb_opentsdb_batch_size                     | 1000                         |             |
| influxdb_opentsdb_batch_pending                  | 5                            |             |
| influxdb_opentsdb_batch_timeout                  | 1s                           |             |
| influxdb_opentsdb_log_point_errors               | true                         |             |
| influxdb_udp_enabled                             | false                        |             |
| influxdb_udp_bind_address                        | ":8089"                      |             |
| influxdb_udp_database                            | udp                          |             |
| influxdb_udp_retention_policy                    | ''                           |             |
| influxdb_udp_batch_size                          | 5000                         |             |
| influxdb_udp_batch_pending                       | 10                           |             |
| influxdb_udp_batch_timeout                       | 1s                           |             |
| influxdb_udp_read_buffer                         | 0                            |             |
| influxdb_udp_precision                           | ''                           |             |
| influxdb_continuous_queries_log_enabled          | true                         |             |
| influxdb_continuous_queries_enabled              | true                         |             |
| influxdb_continuous_queries_run_interval         | 1s                           |             |

Dependencies
------------

None

Example Playbook
----------------

Install InfluxDB
```yaml
- hosts: all
  roles:
    - kbrebanov.influxdb
```

License
-------

BSD

Author Information
------------------

Kevin Brebanov
