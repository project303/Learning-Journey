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
