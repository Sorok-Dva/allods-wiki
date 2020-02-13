Server Hardware Requirements
====

Server config for server operations
--

This values are the official internal recommendations from Allods Team.

|      Part     | Configuration                                                           | Stands for                    | OS                                   | Soft                         |
|:-------------:|-------------------------------------------------------------------------|-------------------------------|--------------------------------------|------------------------------|
| Shard Part    | 2x4x2,83GHz/ /no 16Gb HDD/NIC*2*1GB                                     | Front End Servers             | Ubuntu Server 10.04LTS Edition/amd64 | n/a                          |
| Shard Part    | 2x4x2,83GHz/ /no HDD/NIC*1GB                                            | GameMechanics Servers         | Ubuntu Server 10.04LTS Edition/amd64 | n/a                          |
| Shard Part    | 2x4x2,5GHz/16Gb/4x300G SAS/HwRaid 10/NIC*1GB                            | StatsAlarm Server             | Ubuntu Server 10.04LTS Edition/amd64 | PstgreSql 8.4                |
| Shard Part    | 2x4x2,5GHz/16Gb/2x300G SAS (Hw Raid-1),  2x160G SSD (Hw Raid-1)/NIC*1GB | Item Server                   | Ubuntu Server 10.04LTS Edition/amd64 | MySql 5.1                    |
| Shard Part    | 2x4x2,5GHz/16Gb/4x300G SAS/HwRaid 10/NIC*1GB                            | Backup Server                 | Ubuntu Server 10.04LTS Edition/amd64 | MySql 5.1 & PostgreSql 8.4 * |
| Base Part     | 2x4x2,83GHz/ /no HDD/NIC*2*1GB                                          | Account Server                | Ubuntu Server 10.04LTS Edition/amd64 | n/a                          |
| Base Part     | 1x4x2,5GHz/8Gb/4x160G SAS/HwRaid 10/NIC*1GB                             | DataBases Server              | Ubuntu Server 10.04LTS Edition/amd64 | PostgreSql 8.4; MySql 5.1    |
| Base Part     | 1x4x2,5GHz/ /no HDD/NIC*1GB 8Gb                                         | ItemMall Server               | Ubuntu Server 10.04LTS Edition/amd64 | n/a                          |
| Base Part     | 2x4x2.5GHz/ /4x300G 16GB SAS/HwRaid 10/NIC*1GB                          | StatsAlarm Server             | Ubuntu Server 10.04LTS Edition/amd64 | PostgreSql 8.4               |
| Base Part     | 1x4x2,5GHz/ /no HDD/NIC*1GB 8Gb                                         | Billing Server                | Ubuntu Server 10.04LTS Edition/amd64 | n/a                          |
| Base Part     | 2x4x2,5GHz/16Gb/4x300G SAS/HwRaid 10/NIC*1GB                            | Backup Server                 | Ubuntu Server 10.04LTS Edition/amd64 | MySql 5.1 & PostgreSql 8.4 * |
| Patch/Torrent | 1x4x2.5GHz /2Gb/2x250 SATA/SoftRaid 1                                   | Patch Server,  TorrentTracker | Ubuntu Server 10.04LTS Edition/amd64 | n/a                          |
| Patch/Torrent | 1x4x2.5GHz/2Gb/2x250Gb SATA/SoftRaid1/SSD Intel X25-E                   | Torrents Seeder               | Ubuntu Server 10.04LTS Edition/amd64 | Transmission/WWW/FTP         |

* Operator must set DBes' replication on those servers.

(!!!) Servers with "no HDD" label may ommit HDDes only if option AllodsServerConfiguration№2 for server deploy is taken

RAID item-server requirements :

- 2xSAS RAID-1: binary log storage, needed for replication and restoring database changelog.
- 2xSSD RAID-1: database storage. Capacity of each drive should not be lower than 160GB, so the higher capacity SSD has, the faster it works.
- It is strongly recommended to set item-server MySQL parameter innodb_flush_log_at_trx_commit = 2, even there is BBU and RAID controller cash-memory.
