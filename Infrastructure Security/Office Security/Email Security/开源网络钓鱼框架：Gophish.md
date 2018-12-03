## 概述
[钓鱼平台gophish](https://github.com/gophish/gophish)

## 安装与使用
### Centos7安装gophish
```
# 下载
wget https://github.com/gophish/gophish/releases/download/0.7.1/gophish-v0.7.1-linux-64bit.zip

# 解压并启动
mkdir -p /app/gophish
unzip gophish-v0.7.1-linux-64bit.zip -d /app/gophish/ && cd /app/gophish/

# 修改配置文件
```

![gophish-1](https://github.com/bloodzer0/Enterprise_Security_Build--Open_Source/raw/master/Infrastructure%20Security/Office%20Security/Email%20Security/img/gophish-1.png)

```
# 执行
./gophish

# 访问
https://192.168.199.5:3333/
# 账号：admin 密码：gophish
```

![gophish-2](https://github.com/bloodzer0/Enterprise_Security_Build--Open_Source/raw/master/Infrastructure%20Security/Office%20Security/Email%20Security/img/gophish-2.png)


### 使用gophish进行钓鱼
* **用户与组信息：Users & Groups**

添加员工邮件信息

![gophish-3](https://github.com/bloodzer0/Enterprise_Security_Build--Open_Source/raw/master/Infrastructure%20Security/Office%20Security/Email%20Security/img/gophish-3.png)

* **配置邮件模板：Email Templates**

![gophish-4](https://github.com/bloodzer0/Enterprise_Security_Build--Open_Source/raw/master/Infrastructure%20Security/Office%20Security/Email%20Security/img/gophish-4.png)

* **配置加载页面：Landing Pages**

![gophish-5](https://github.com/bloodzer0/Enterprise_Security_Build--Open_Source/raw/master/Infrastructure%20Security/Office%20Security/Email%20Security/img/gophish-5.png)

* 配置发件人信息：Sending Profiles

![gophish-6](https://github.com/bloodzer0/Enterprise_Security_Build--Open_Source/raw/master/Infrastructure%20Security/Office%20Security/Email%20Security/img/gophish-6.png)

* 测试发件人信息是否正确

![gophish-7](https://github.com/bloodzer0/Enterprise_Security_Build--Open_Source/raw/master/Infrastructure%20Security/Office%20Security/Email%20Security/img/gophish-7.png)

![gophish-8](https://github.com/bloodzer0/Enterprise_Security_Build--Open_Source/raw/master/Infrastructure%20Security/Office%20Security/Email%20Security/img/gophish-8.png)

* **配置发送信息**

![gophish-9](https://github.com/bloodzer0/Enterprise_Security_Build--Open_Source/raw/master/Infrastructure%20Security/Office%20Security/Email%20Security/img/gophish-9.png)

![gophish-10](https://github.com/bloodzer0/Enterprise_Security_Build--Open_Source/raw/master/Infrastructure%20Security/Office%20Security/Email%20Security/img/gophish-10.png)

![gophish-11](https://github.com/bloodzer0/Enterprise_Security_Build--Open_Source/raw/master/Infrastructure%20Security/Office%20Security/Email%20Security/img/gophish-11.png)
