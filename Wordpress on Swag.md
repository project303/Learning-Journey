## Service di docker compose
```
  wp-dev02:
    depends_on:
      - mariadb
    image: wordpress:latest
    container_name: wp-dev02
    volumes:
      - ./data/wp-dev02:/var/www/html
    restart: always
    ports:
      - "49082:80"
    environment:
      WORDPRESS_DB_HOST: mariadb:3306
      WORDPRESS_DB_USER: wordpress
      WORDPRESS_DB_PASSWORD: Admin247#
      WORDPRESS_DB_NAME: wp-dev02
    networks:
      - net
```

## Routing port di SWAG
File: /home/admin247/swag/data/swag/nginx/site-confs/default.conf

```
# wp-dev02
server {
    listen 8882 ssl;
    listen [::]:8882 ssl;
    listen learn.solusi247.com:8882 ssl;
    server_name learn.solusi247.com;

    include /config/nginx/ssl.conf;

    client_max_body_size 0;

    location / {
        include /config/nginx/proxy.conf;
        include /config/nginx/resolver.conf;

        # ip internal
        set $upstream_app 172.20.3.120;
        set $upstream_port 49082;
        set $upstream_proto http;
        proxy_pass $upstream_proto://$upstream_app:$upstream_port;
    }
}
```


