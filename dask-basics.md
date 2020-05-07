# Dask Basics

**Note:** Dask is all about Parallelism



Install Dask:
```
conda activate py36
conda install dask
```

How to run a Dask sceduler?
```
dask-scheduler
```
You should see the logs like below:
```
distributed.scheduler - INFO - Clear task state
distributed.scheduler - INFO -   Scheduler at:   tcp://192.168.2.26:8786
distributed.scheduler - INFO -   dashboard at:                     :8787
```

How to run woker(s)?
```
dask-worker tcp://192.168.2.26:8786
```
You should see logs like below in your scheduler console:
```
Register worker <Worker 'tcp://192.168.2.26:64764', name: tcp://192.168.2.26:64764, memory: 0, processing: 0>
distributed.scheduler - INFO - Starting worker compute stream, tcp://192.168.2.26:64764
```

How to connect from a client?
```
from dask.distributed import Client
client = Client("tcp://192.168.2.26:8786")
```

How to remove worker?
```
just close the running worker console

You should see the logs like below:
Remove worker <Worker 'tcp://192.168.2.26:64796', name: tcp://192.168.2.26:64796, memory: 0, processing: 0>
distributed.core - INFO - Removing comms to tcp://192.168.2.26:64796
```

[Dask Setup and Basics](https://www.youtube.com/watch?v=TQM9zIBzNBo)