# DB/사용자 생성하기

## 1. 사용자 추가

```aspnet
# su - postgres -c 'psql'
postgres=# CREATE USER test PASSWORD 'test' SUPERUSER;
```

## 2. 데이터베이스 추가

```aspnet
postgres=# CREATE DATABASE testdb OWNER test;
```

## 3. 데이터베이스 접속

```aspnet
postgres=# \c testdb test
testdb=# <SQL...>
```

