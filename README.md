### Surrogate

A simple bash wrapper for Percona's Xtrabackup utility.

----

### Prerequisites

- Qpress, included in the installer, otherwise you can get a copy [here.](http://www.quicklz.com/qpress-11-linux-x64.tar)

- Percona 5.5+
- Percona Xtrabackup 2.0.1 or later
- Ample disk space (even with compression backups are only 2:1 ratio)

#### Usage

`sh surrogate -<flag> <argument>`

- -h	Usage
- -b	Performs a backup, either incremental or full depending on the argument you supply, for example: "surrogate -b full"
--	Accepts either "full" or "inc" as an argument
- -r  Restore using default digest location
- -c  Restore, accepts a file containing a list of directories to restore.


#### Configuration

Main configuration file
- /etc/surrogate/surrogate.conf

#### Retention directory tree 

    /var/backups/db/percona/ (customizable data directory)
    |-- daily
    |   |-- Fri
    |   |-- Mon
    |   |-- Sat
    |   |-- Sun
    |   |-- Thu
    |   |-- Tue
    |   `-- Wed
    |-- monthly
    |-- weekly
    |-- log
    |-- tmp

#### Default rotation policy (configurable in surrogate.conf)

- 7 days
- 4 weeks
- 6 months

#### Authors

- [Loren Carvalho](https://github.com/sixninetynine)
- [Jesse R. Adams](https://github.com/jesseadams)
- [Ivan Y.](https://github.com/yagodin-pro)

#### License

GPLv3
