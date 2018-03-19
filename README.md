# FrontierSurvey
前沿技术资料汇总

### 环境配置
clone仓库：
```
git clone https://github.com/RoadConditionGroup/FrontierSurvey.git
```

提交：
```
git add .
git commit -m 'comments'
git push
```

**首次提交需要在github上添加ssh-key** [地址](https://github.com/settings/keys)

ssh-key生成方法
```
ssh-keygen -t rsa -C 'yourRTX@tencent.com'
```

**公司内需要设置代理**，配置文件
```
C:\Users\jensonjiang\.ssh\config
```

配置文件内容举例：
```
protocol 2
serverAliveInterval 6

Host github.com
    User git
    Port 22
    Hostname github.com
    IdentityFile "C:/Users/jensonjiang/.ssh/id_rsa"
    ProxyCommand "C:/Program Files/Git/mingw64/bin/connect.exe" -H dev-proxy.oa.com:8080 %h %p
```

已在其他github账号中添加的ssh-key，不允许再添加到其他账号。因此，需要生成一个新的ssh-key，并相应配置config文件，例如添加下面几行
```
Host github2.com
    User git
    Port 22
    Hostname github.com
    IdentityFile "C:/Users/jensonjiang/.ssh/id_rsa_tencent"
    ProxyCommand "C:/Program Files/Git/mingw64/bin/connect.exe" -H dev-proxy.oa.com:8080 %h %p
```

然后修改push地址，方法为
```
git remote set-url origin github2:RoadConditionGroup/FrontierSurvey.git
```

详情可以参考[网址](https://www.webmaster.me/uncategorized/add-multiple-ssh-keys-on-github.html)
