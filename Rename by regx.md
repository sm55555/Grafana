
### Rename by regx

<img width="659" alt="image" src="https://github.com/sm55555/Grafana/assets/38831314/9bed22ea-9bb0-49bd-8f04-d2d867ca7b4f">

예를들어 Legend 값이 아래와 같이 형성되어 있으면

```
test/a/UserA
test/b/UserB
test/c/UserC
test/d/UserD
```

Match를 아래와 같이 Rename이 가능하다.

```
Rename : test/a/([^]+)/
Replace : Created By 
```

결과

```
Created By UserA
Created By UserB
Created By UserC
Created By UserD
```


