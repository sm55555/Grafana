## 1. slack webhook 생성 하기


## 2. Alerting 만들기 Alert rules, Contact points

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

## 3. Contact points Template 넣기

하단에 있는 mymessage에 template를 적용하면 된다.

<img width="507" alt="image" src="https://github.com/sm55555/Grafana/assets/38831314/bdcbfdab-0f6d-44cb-9471-e11f2853ea88">

## 4. Alert Rule 작성 방법

![image](https://github.com/sm55555/Grafana/assets/38831314/a9656553-5b80-4cce-aa41-cd3ce58e7664)






