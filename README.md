Ansible Role: ansible_role_cassandra
=========

Installs and configures Apache Cassandra, a scalable NoSQL database, on Enterprise Linux version 7 or greater.

Requirements
------------

This role requires the following Ansible collections:

- `ansible.posix`
- `community.crypto`
- `community.general`

You can install these collections using the following command:

```shell
ansible-galaxy collection install ansible.posix community.crypto community.general
```

Role Variables
--------------

| Variable | Default | Comments |
| -------- | ------- | -------- |
| `ansible_role_cassandra_allocate_tokens_for_local_replication_factor` | 3 | Tokens allocated per node for local replication. |
| `ansible_role_cassandra_batch_size_fail_threshold` | '50KiB' | Maximum batch size before write fails. |
| `ansible_role_cassandra_batch_size_warn_threshold` | '5KiB' | Maximum batch size before warning is logged. |
| `ansible_role_cassandra_cas_contention_timeout` | '1000ms' | Timeout for compare-and-set operations. |
| `ansible_role_cassandra_cluster_name` | 'vCD Performance Metrics' | Name of the Cassandra cluster. |
| `ansible_role_cassandra_cql_ips` | ['127.0.0.1'] | List of IP addresses for CQL communication. |
| `ansible_role_cassandra_commitlog_segment_size` | '32MiB' | Size of each commit log segment. |
| `ansible_role_cassandra_commitlog_sync_period` | '10s' | Interval for syncing the commit log to disk. |
| `ansible_role_cassandra_commitlog_sync` | 'periodic' | Method of syncing the commit log. |
| `ansible_role_cassandra_compaction_large_partition_warning_threshold` | '100MiB' | Threshold for large partition warning during compaction. |
| `ansible_role_cassandra_compaction_throughput` | '64MiB/s' | Compaction throughput in MiB/s. |
| `ansible_role_cassandra_concurrent_reads` | 32 | Number of concurrent read operations. |
| `ansible_role_cassandra_concurrent_writes` | 32 | Number of concurrent write operations. |
| `ansible_role_cassandra_counter_write_request_timeout` | '5000ms' | Timeout for counter write requests. |
| `ansible_role_cassandra_jmx_ips` | ['127.0.0.1'] | List of IP addresses for JMX communication. |
| `ansible_role_cassandra_keystore_password` | 'changeit' | Password for the keystore. |
| `ansible_role_cassandra_listen_address` | | IP address for Cassandra to listen on. |
| `ansible_role_cassandra_manage_firewall` | true | Whether to manage the firewall. |
| `ansible_role_cassandra_manage_firewalld` | true | Whether to manage firewalld. |
| `ansible_role_cassandra_max_hints_delivery_threads` | 2 | Maximum number of threads for delivering hints. |
| `ansible_role_cassandra_nodes` | [] | List of Cassandra nodes with names and IPs. |
| `ansible_role_cassandra_num_tokens` | 16 | Number of tokens for the node. |
| `ansible_role_cassandra_password` | | Password for Cassandra. |
| `ansible_role_cassandra_prefer_ipv6` | false | Whether to prefer IPv6 addresses. |
| `ansible_role_cassandra_range_request_timeout` | '10000ms' | Timeout for range requests. |
| `ansible_role_cassandra_read_request_timeout` | '5000ms' | Timeout for read requests. |
| `ansible_role_cassandra_rpc_address` | | RPC address for Cassandra. |
| `ansible_role_cassandra_seeds` | | List of seed nodes for Cassandra. |
| `ansible_role_cassandra_ssl_cert` |  | SSL certificate path. |
| `ansible_role_cassandra_ssl_enable` | false | Whether to enable SSL. |
| `ansible_role_cassandra_ssl_key_password` | 'changeit' | Password for SSL key. |
| `ansible_role_cassandra_ssl_key` |  | SSL key path. |
| `ansible_role_cassandra_trickle_fsync_interval` | '10240KiB' | Interval for trickle fsync in KiB. |
| `ansible_role_cassandra_truststore_password` | 'changeit' | Password for the truststore. |
| `ansible_role_cassandra_write_request_timeout` | '2000ms' | Timeout for write requests. |


Dependencies
------------

This role has no external dependencies.

Example Playbook
----------------

    - hosts: servers

      vars:
        ansible_role_cassandra_allocate_tokens_for_local_replication_factor: 3
        ansible_role_cassandra_batch_size_fail_threshold: 50KiB
        ansible_role_cassandra_batch_size_warn_threshold: 5KiB
        ansible_role_cassandra_cas_contention_timeout: 1000ms
        ansible_role_cassandra_cluster_name: vCD Performance Metrics
        ansible_role_cassandra_cql_ips:
        - '127.0.0.1'
        ansible_role_cassandra_commitlog_segment_size: 32MiB
        ansible_role_cassandra_commitlog_sync_period: 10s
        ansible_role_cassandra_commitlog_sync: periodic
        ansible_role_cassandra_compaction_large_partition_warning_threshold: 100MiB
        ansible_role_cassandra_compaction_throughput: 64MiB/s
        ansible_role_cassandra_concurrent_reads: 32
        ansible_role_cassandra_concurrent_writes: 32
        ansible_role_cassandra_counter_write_request_timeout: 5000ms
        ansible_role_cassandra_jmx_ips:
        - '127.0.0.1'
        ansible_role_cassandra_keystore_password: changeit
        ansible_role_cassandra_listen_address: 10.0.2.15
        ansible_role_cassandra_manage_firewall: true
        ansible_role_cassandra_manage_firewalld: true
        ansible_role_cassandra_max_hints_delivery_threads: 2
        ansible_role_cassandra_nodes:
        - name: 'rocky91'
            ip: '10.0.2.15'
        ansible_role_cassandra_num_tokens: 16
        ansible_role_cassandra_password: 'Correct Horse Battery Staple'
        ansible_role_cassandra_prefer_ipv6: false
        ansible_role_cassandra_range_request_timeout: 10000ms
        ansible_role_cassandra_read_request_timeout: 5000ms
        ansible_role_cassandra_rpc_address: 10.0.2.15
        ansible_role_cassandra_seeds:
        - 'rocky91'
        ansible_role_cassandra_ssl_cert:
        ansible_role_cassandra_ssl_enable: false
        ansible_role_cassandra_ssl_key_password: changeit
        ansible_role_cassandra_ssl_key:
        ansible_role_cassandra_trickle_fsync_interval: 10240KiB
        ansible_role_cassandra_truststore_password: changeit
        ansible_role_cassandra_write_request_timeout: 2000ms

      roles:
         - ansible_role_cassandra

License
-------

MIT

Author Information
------------------

Mattias Jonsson
