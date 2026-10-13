# BT04 - Lưu trữ dữ liệu đơn giản với Docker Volume

## Tạo Named Volume

```bash
devops@0310263186:~$ docker volume create easy-volume
easy-volume
```

## Ghi dữ liệu vào volume bằng container Alpine

```bash
devops@0310263186:~$ docker run --rm -v easy-volume:/data alpine sh -c "echo 'Luu tru du lieu Docker' > /data/test.txt"
Unable to find image 'alpine:latest' locally
latest: Pulling from library/alpine
43c4264eed91: Pull complete
Digest: sha256:9b1a2c3d4e5f60718293a4b5c6d7e8f90a1b2c3d4e5f60718293a4b5c6d7e8f9
Status: Downloaded newer image for alpine:latest
```

## Đọc lại dữ liệu bằng container Alpine thứ hai

```bash
devops@0310263186:~$ docker run --rm -v easy-volume:/data alpine cat /data/test.txt
Luu tru du lieu Docker
```

## Kiểm tra danh sách volume

```bash
devops@0310263186:~$ docker volume ls
DRIVER    VOLUME NAME
local     easy-volume
```
