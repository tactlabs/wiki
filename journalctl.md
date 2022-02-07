/ [Home](index.md)

# Journalctl Commands

```
journalctl --since "2022-02-01"

journalctl --since "2022-02-01 00:24:41" --until "2022-02-02"

journalctl --since "2022-02-01 00:24:41" --until "2022-02-02"
-- Logs begin at Wed 2021-10-20 22:45:54 UTC, end at Tue 2022-02-01 00:17:16 UTC. --
-- No entries --

Save to log:
journalctl --since "2022-02-01 00:24:41" --until "2022-02-02" >> minio_error.log

journalctl --since "2022-02-07 14:20:45"
```