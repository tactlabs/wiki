/ [Home](index.md)

# Luigi

**Note:** notes



Clone the Docker
```
git clone git@github.com:spiside/docker-luigi.git
```



```
cd docker-luigi
./luigi setup
```




Verify
```
docker ps --filter "name=luigi"
```



Get into Container shell
```
./luigi shell
```

```
python -m src.tasks.example RunAllTasks
```


```
./luigi up
```

```
./luigi down
```


```
./luigi stop
```


Debugging
```
./luigi logs -f <optional: docker-compose service name>
```

### Ref :

  * [Luigi Docker](https://github.com/spiside/docker-luigi)
  * [Official Docs](https://luigi.readthedocs.io/en/stable/)
  * [DB Entry](http://engineering.pivotal.io/post/luigi-data-science/)
  * [Luigi Warehouse](https://github.com/groupon/luigi-warehouse)
  * [SQL Table Entry](https://luigi.readthedocs.io/en/latest/api/luigi.contrib.sqla.html)
  * [Postgres](https://github.com/iamaaronknight/luigi-exercise-template)
  * [Spotify ](https://github.com/spotify/luigi/blob/master/examples/top_artists.py)
  * [Top Artists](https://luigi.readthedocs.io/en/stable/example_top_artists.html)
  * [Luigi Docs](https://manualzz.com/doc/2985824/luigi-documentation)