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

## 高级使用
### 使用gophish钓用户账号密码信息
* **首先，需要配置一个Sending Profiles，与上面的配置一致即可；**

* **其次，配置一个Landing Pages；**

```
# 我随便找了一个地址，导入站点，设置Redirect也为这个地址
http://xnore.com/admin/login.php
```

![gophish-12](https://github.com/bloodzer0/Enterprise_Security_Build--Open_Source/raw/master/Infrastructure%20Security/Office%20Security/Email%20Security/img/gophish-12.png)

![gophish-13](https://github.com/bloodzer0/Enterprise_Security_Build--Open_Source/raw/master/Infrastructure%20Security/Office%20Security/Email%20Security/img/gophish-13.png)

* **配置一个模版Email Templates**

首先找到一封邮件，查看源代码，复制源代码信息

![gophish-14](https://github.com/bloodzer0/Enterprise_Security_Build--Open_Source/raw/master/Infrastructure%20Security/Office%20Security/Email%20Security/img/gophish-14.png)

![gophish-15](https://github.com/bloodzer0/Enterprise_Security_Build--Open_Source/raw/master/Infrastructure%20Security/Office%20Security/Email%20Security/img/gophish-15.png)

![gophish-16](https://github.com/bloodzer0/Enterprise_Security_Build--Open_Source/raw/master/Infrastructure%20Security/Office%20Security/Email%20Security/img/gophish-16.png)

* **配置一个Campaigns**

![gophish-17](https://github.com/bloodzer0/Enterprise_Security_Build--Open_Source/raw/master/Infrastructure%20Security/Office%20Security/Email%20Security/img/gophish-17.png)

然后去我们的邮箱，点击邮件中的url（备注：我这里gophish的地址由上文的192.* 变化为10.10.10.5）

![gophish-18](https://github.com/bloodzer0/Enterprise_Security_Build--Open_Source/raw/master/Infrastructure%20Security/Office%20Security/Email%20Security/img/gophish-18.png)

![gophish-19](https://github.com/bloodzer0/Enterprise_Security_Build--Open_Source/raw/master/Infrastructure%20Security/Office%20Security/Email%20Security/img/gophish-19.png)

![gophish-20](https://github.com/bloodzer0/Enterprise_Security_Build--Open_Source/raw/master/Infrastructure%20Security/Office%20Security/Email%20Security/img/gophish-20.png)

这个时候如果用户在页面输入了信息，我们来看一下变化

![gophish-21](https://github.com/bloodzer0/Enterprise_Security_Build--Open_Source/raw/master/Infrastructure%20Security/Office%20Security/Email%20Security/img/gophish-21.png)

![gophish-22](https://github.com/bloodzer0/Enterprise_Security_Build--Open_Source/raw/master/Infrastructure%20Security/Office%20Security/Email%20Security/img/gophish-22.png)


### 后续玩法
后续我们就可以构建更多的信息来收集是谁点击的，主要是做一个好的登录页面。
