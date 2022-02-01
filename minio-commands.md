/ [Home](index.md)

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
How to run Minio in the background
```
import os
os.system ("MINIO_ROOT_USER=<ACCESS_KEY> MINIO_ROOT_PASSWORD=<PASS_KEY> minio server ./data{1...5} --console-address :9001")
```
How to run Minio in the background in the detached mode with Docker
```
sudo docker run -d  \ 
	  -p 9000:9000 \
	  -p 9001:9001 \
	  -e "MINIO_ROOT_USER=<ACCESS_KEY>" \
	  -e "MINIO_ROOT_PASSWORD=<PASS_KEY>" \
	  quay.io/minio/minio server /data --console-address ":9001"   
```


### Ref :

  * [Name](file)
  * []()
  * []()
