# docker-compose

## 服务启动/停止

```
docker-compose up
docker-compose stop
docker-compose up {service_name}
docker-compose up {service_name} -d
```

## 服务启动日志

```
docker logs -f {service_name}
```

## 服务登录

```
docker exec -it {service_name} sh
```

## 注意事项

```
因为数据库文件是放在宿主机的，映射到容器内部。导致每次容器启动的时候，会去判断数据库文件是否被初始化。 我发现，如果文件被初始化后，就不会去执行MYSQL_ROOT_PASSWORD设置的密码。

修改密码，需删除数据库文件，才会生效
```

## 清除缓存

```
docker-compose rm {service_name}
docker-compose up
```
