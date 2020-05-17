# MinIO Commands

**Note:** notes



Basic Docker
```
docker run -p 9000:9000 minio/minio server /data
minioadmin / minioadmin
```

Docker with commands
```
docker service create \
--name minio \
--network appnet \
--replicas 1 \
--publish 9000:9000 \
--constraint 'node.role==manager' \
-e "MINIO_ACCESS_KEY=ASDFASDFASDF" \
-e "MINIO_SECRET_KEY=ASDFASDFASDF" \
--mount "type=bind,source=/mnt/data,target=/data" \
minio/minio server /data
```



### Ref :

  * [Name](file)
  * []()
  * []()
