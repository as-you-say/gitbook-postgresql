# 설치하기

## 1.저장소 등록

```text
# sudo rpm -Uvh https://download.postgresql.org/pub/repos/yum/reporpms/EL-7-x86_64/pgdg-redhat-repo-latest.noarch.rpm
```

## ‌2. 설치

```text
# sudo yum install -y postgresql11-server postgresql11-contrib
```

## ‌3. 데이터베이스 초기화

```text
# sudo /usr/pgsql-11/bin/postgresql-11-setup initdb
```

## ‌4. 서비스 실행 및 등록

```text
# sudo systemctl start postgresql-11
# sudo systemctl enable postgresql-11
```

## ‌5. 사용자 비밀번호 변경

```text
# su - postgres -c 'psql'
postgres=# ALTER USER postgres PASSWORD <new_password>;
```

## ‌6. 환경설정 파일 수정

```text
# vi /var/lib/pgsql/11/data/postgresql.conf​

<postgresql.conf>
listen_addresses = '*'
```

```text
# vi /var/lib/pgsql/11/data/pg_hba.conf​

<pg_hba.conf>
# TYPE  DATABASE        USER            ADDRESS                 METHOD
host    all             all             0.0.0.0/0               md5
local   all             all                                     md5
host    all             all             127.0.0.1/32            ident
host    all             all             ::1/128                 ident
​# replication privilege.
local   replication     all                                     peer
host    replication     all             127.0.0.1/32            ident
host    replication     all             ::1/128                 ident
```

```text
# sudo service postgresql-11 restart
```

