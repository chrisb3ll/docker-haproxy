# docker-haproxy

Environment Variables
```
-e HAPROXY_FRONTEND_PORT=80
-e HAPROXY_BACKEND_HOST=nginxproxy
-e HAPROXY_BACKEND_PORT=80
-e HAPROXY_STRIP_PATH=socket
```

Example
```
docker run -it \
  --network proxy \
  -e HAPROXY_BACKEND_HOST=nginxproxy \
  -e HAPROXY_BACKEND_PORT=80 \
  -e HAPROXY_FRONTEND_PORT=80 \
  -e HAPROXY_STRIP_PATH=socket  \
  -v $(pwd)/haproxy.cfg:/usr/local/etc/haproxy/haproxy.cfg:ro \
  -p 8081:80 \
  haproxy:1.8-alpine
```
