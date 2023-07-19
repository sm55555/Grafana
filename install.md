
### 일반 다운 방법

```
sudo yum install -y https://dl.grafana.com/enterprise/release/grafana-enterprise-10.0.2-1.x86_64.rpm
```


### Repo 통해서 다른곳에서 받을때

다운로드 시 font 관련 RPM이 딸려온다...

```
sudo yum install https://dl.grafana.com/enterprise/release/grafana-enterprise-10.0.2-1.x86_64.rpm  --downloadonly --downloaddir=[PATH]
sudo yum reinstall https://dl.grafana.com/enterprise/release/grafana-enterprise-10.0.2-1.x86_64.rpm  --downloadonly --downloaddir=[PATH]
```


##### 아래 주소 참고

https://grafana.com/grafana/download
