## 概述
[下载地址](https://sourceforge.net/projects/rips-scanner/files/)

RIPS静态的代码分析工具，能自动化挖掘PHP代码漏洞。

## 安装与使用

```
yum install php httpd.x86_64 -y
systemctl start httpd.service

wget https://nchc.dl.sourceforge.net/project/rips-scanner/rips-0.55.zip

unzip rips-0.55.zip
```

填写网站路径就可以开始扫描，扫描结果如下：

![rips](https://github.com/bloodzer0/Enterprise_Security_Build--Open_Source/raw/master/Application%20Security/Code%20Audit/img/rips-1.png)

## 我的一点感悟
* 对PHP项目支持比较友好，对其他语言类项目支持一般；
* 与法师的代码审计工具很类似；

## 参考资料
[RIPS源码精读：逻辑流程及lib文件夹大致说明](https://xz.aliyun.com/t/2502)

[RIPS源码精读：扫描对象的实例化及token信息的生成](https://xz.aliyun.com/t/2605)
