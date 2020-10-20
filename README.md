# ghost-blog-compose
 
### * Create docker network
``` 
docker network create nginx-proxy 
```
 
### * Create nginx-proxy
``` 
docker run -d -p 80:80 --name nginx-proxy --net nginx-proxy -v /var/run/docker.sock:/tmp/docker.sock jwilder/nginx-proxy 
```

### * Run blog
``` 
docker run -d --name bloghost --expose 2368 -e url=http://localhost.blog -e VIRTUAL_HOST=localhost.blog ghost:latest 
``` 

or with `docker-compose`
``` 
docker-compose up -d 
```
 
