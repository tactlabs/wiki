/ [Home](index.md)

## ML Issues

### 1
```
I have tried many parallelized python data manipulation tools, and pandarallel was one of them. Despite its undeniable convenience, there is a serious memory issue with pandarallel. Since it utilizes python multiprocessing to parallelize tasks, it requires a copy of the original dataframe for every process that it spawns. 

It means that if you set pandarallel to spawn 16 processes, and your dataframe occupies 8GB of memory, it will cost you 128GB RAM to complete the computation, which is huge and can cause an instant crash. 

I would suggest polars as a powerful pandas/pyspark/dask alternative for single-machine out-of-memory parallelized computing. Unlike pandas, polars was implemented with the strong support for concurrency in Rust to run operations in parallel. 

Its eager API and lazy API are also extremely helpful for out-of-memory computing and implementing custom transformations instead of relying on Python functions/lambdas like pandas. 

Polars is quite suitable for many of us who often have access to google colabs, kaggle kernel, or a single workstation with mid-end/high-end computing power (32-64 CPU cores and 64-128GB RAM).


Have you executed your code? Actually I have just re-read the implementation of pandarallel and the author seems to be aware of this issue so he used pipe or file system to avoid duplicating the original dataframe. 

However the last time I used pandarallel, I got some deadlock issues that I had to eventually implement my own multiprocessing pipeline to overcome the issue. 

I doubt that your implementation will copy the data around. I believe that tools like polars which utilizes multithreading without the GIL will be much more suitable for parallelizing data trasformations instead of using multiprocessing to "unlock" the GIL in Python.

https://www.linkedin.com/posts/khuyen-tran-1401_python-activity-7007017519542657024-x6o3?utm_source=share&utm_medium=member_desktop
```

### Subtitlte:

* [ABC](link)

* [XYZ](link)

### Ref :

  * []()
