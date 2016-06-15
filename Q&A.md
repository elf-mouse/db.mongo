__Q:__ Failed global initialization: BadValue Invalid or no user locale set. Please ensure LANG and/or LC_* environment variables are set correctly.

__A:__ `export LC_ALL=C`

---

__Q:__ WARNING: You are running this process as the root user, which is not recommended.

__A:__

```
useradd mdb

cp /path/to/mongodb /home/mdb
chown -R mdb:mdb /home/mdb/mongodb

rm -rf /tmp/mongodb-*

su - mdb

vi .bash_profile
export PATH=/home/mdb/mongodb/bin:$PATH

mongod
```

---

__Q:__

```
WARNING: /sys/kernel/mm/transparent_hugepage/enabled is 'always'.
We suggest setting it to 'never'
WARNING: /sys/kernel/mm/transparent_hugepage/defrag is 'always'.
We suggest setting it to 'never'
```

__A:__ [Disable Transparent Huge Pages (THP)](https://docs.mongodb.com/manual/tutorial/transparent-huge-pages/#transparent-huge-pages-thp-settings)

---

__Q:__ WARNING: soft rlimits too low. rlimits set to 1024 processes, 65535 files. Number of processes should be at least 32767.5 : 0.5 times number of files.

__A:__ [UNIX ulimit Settings](https://docs.mongodb.com/v3.0/reference/ulimit/)
