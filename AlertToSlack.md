#### 1. slack webhook 생성 하기


#### 2. Alerting 만들기 Alert rules, Contact points

원본 데이터

```
[FIRING:1]  (test)
**Firing**
Value: [ var='B0' metric='value' labels={Records.requestParameters.userName.keyword=iamtest, Records.userIdentity.arn.keyword=arn:aws:sts::111122223333:assumed-role/AWSReservedSSO_Platform-SE-Permission_04b811080c850109/test} value=361 ]
Labels:
- alertname = test
Annotations:
Source: http://172.0.0.0:3000/alerting/grafana/OdULVlrVz/view
```

여기서 필요한 데이터는 labels 안에 있는것들


template 예제
```yaml


{{ define "test-template"}}
{{ range .Alerts }}
*IAM_User*: {{ reReplaceAll "(.*) (labels=)({Records.requestParameters.userName.keyword=)(.*)(,)(.*)(}) (.*)" "$4" .ValueString}}
*Created By*: {{ reReplaceAll "(.*) (labels=)(.*)(, Records.userldentity.arn.keyword=)(.*)(}) (*)" "$5" ValueString}}
{{ end}}
{{ end}}

```
