# 외부에서 접속하기

## 1. 포트 확인 <a id="1"></a>

```text
# cat /etc/services | grep postgresql*
postgres        5432/tcp        postgresql      # POSTGRES
postgres        5432/udp        postgresql      # POSTGRES
```

## 2. 방화벽 허용 <a id="2"></a>

```text
# firewall-cmd --zone=public --permanent --add-port=5432/tcp
# firewall-cmd --reload
```

## 3. 데이터베이스 정보 <a id="3"></a>

| No | Property | Value |
| :---: | :---: | :---: |
| 1 | Host | localhost |
| 2 | Port | 5432 |
| 3 | Database | testdb |
| 4 | User | test |
| 5 | Password | test |

![](https://gblobscdn.gitbook.com/assets%2F-MB2nJLjZYVpIePzpLXN%2F-MB2x_GTdwvUCaPYNKY4%2F-MB2zerxaY-lY7CwUJkc%2Fimage.png?alt=media&token=e7612ad7-6df5-4152-ac15-de3cce0315bb)

