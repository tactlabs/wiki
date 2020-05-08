# CURL Basics

**Note:** tbw



Simple GET
```
curl -X GET 'https://reqres.in/api/users/3'
```






Simple GET with Echo
```
curl http://ipecho.net/plain; echo
```






Simple POST
```
curl -XPOST "http://localhost:5000/image" -d '{"image_data" : "'"$( base64 test_images/11.png)"'"}'
```







```
curl -XPOST "http://localhost:5000/image" -H "Content-Type: application/json" -d '{"image_data" : "'"$( base64 test_images/2.png)"'"}'
```







```
curl -XPOST "http://localhost:5000/image-sync" -d '{"image_data" : "'"$( base64 test_images/4.png)"'"}'
```







```

```







```

```







```

```







```

```







```

```







```

```







```

```







```

```







```

```







```

```







```

```







```

```







```

```
