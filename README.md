### 生成随机SECRET_KEY

```
$ cat /dev/urandom | tr -dc A-Za-z0-9 | head -c 50
```

MacOS:
```
$ cat /dev/urandom | LC_CTYPE=C tr -dc A-Za-z0-9 | head -c 50
```

### 生成随机BOOTSTRAP_TOKEN

```
$ cat /dev/urandom | tr -dc A-Za-z0-9 | head -c 16
```

MacOS:
```
$ cat /dev/urandom | LC_CTYPE=C tr -dc A-Za-z0-9 | head -c 16
```

### Jumpserver访问方式

请打开浏览器访问公网80端口，用户名: admin 密码: admin