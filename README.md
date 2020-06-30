# 설치하기

## 1.저장소 등록

```text
# sudo rpm -Uvh https://download.postgresql.org/pub/repos/yum/reporpms/EL-7-x86_64/pgdg-redhat-repo-latest.noarch.rpm
```

‌

## 2. 설치 <a id="2"></a>

```text
# sudo yum install -y postgresql11-server postgresql11-contrib
```

‌

## 3. 데이터베이스 초기화 <a id="3"></a>

```text
# sudo /usr/pgsql-11/bin/postgresql-11-setup initdb
```

‌

## 4. 서비스 실행 및 등록 <a id="4"></a>

```text
# sudo systemctl start postgresql-11# sudo systemctl enable postgresql-11
```

‌

## 5. 사용자 비밀번호 변경 <a id="5"></a>

```text
# su - postgres -c 'psql'postgres=# ALTER USER postgres PASSWORD <new_password>;
```

‌

## 6. 환경설정 파일 수정 <a id="6"></a>

```text
# vi /var/lib/pgsql/11/data/postgresql.conf​<postgresql.conf>listen_addresses = '*'
```

```text
# vi /var/lib/pgsql/11/data/pg_hba.conf​<pg_hba.conf># TYPE  DATABASE        USER            ADDRESS                 METHODhost    all             all             0.0.0.0/0               md5local   all             all                                     md5host    all             all             127.0.0.1/32            identhost    all             all             ::1/128                 ident​# replication privilege.local   replication     all                                     peerhost    replication     all             127.0.0.1/32            identhost    replication     all             ::1/128                 ident
```

```text
# sudo service postgresql-11 restart
```

