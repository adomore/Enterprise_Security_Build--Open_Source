# splunk安装与基础使用



## 获取安装包

| 系统类型 |          系统兼容版本           | 支持系统版本                                                 |
| -------- | :-----------------------------: | ------------------------------------------------------------ |
| Windows  |             32-bit              | Windows 8.1, and 10                                          |
| Windows  |             64-bit              | Windows 8.1, and 10 <br/> Windows Server 2012 and 2012 R2, and 2016 |
| Linux    | 2.6+ kernel Linux distributions | RHEL/Centos/<br/>Ubuntu/Debian等Linux发布版本                |
| macOS    |               ---               | OSX 10.11 <br/>OSX 10.12 和OSX 10.13                         |


1、获取方式分为两种：

- 通过命令行下载（wget）
- 通过浏览器下载

2、下载地址：https://www.splunk.com/zh-hans_cn/download/

![](C:\Users\Administrator\Desktop\splunk-img\splunk安装\splunk-1.png)

3、备份下载地址：



## Windows安装splunk

双击splunk，然后勾选 `check this to accept the License Agreement` ，然后进行下一步。

![](C:\Users\Administrator\Desktop\splunk-img\splunk安装\18.png)

为了splunk配置WEB管理界面的账号密码。

![](C:\Users\Administrator\Desktop\splunk-img\splunk安装\19.png)

创建开始菜单快捷方式，点击`Intsall` 开始安装。

![](C:\Users\Administrator\Desktop\splunk-img\splunk安装\20.png)

等待少许时刻，安装成功后选择`Launch browser with Splunk Enterprise`,通过浏览器打开应用界面。

![](C:\Users\Administrator\Desktop\splunk-img\splunk安装\21.png)

![](C:\Users\Administrator\Desktop\splunk-img\splunk安装\22.png)

- [x] **注意**

  1、Windows下安装splunk可能会出现splunkweb服务在传统模式下（legacy purposes only）无法启动的情况。解决方案为：

  ```shell
  # %SPLUNK_HOME%在Windows下默认为C:\Program Files\Splunk\
  打开%SPLUNK_HOME%\etc\system\local目录，找到web.conf这配置文件
  然后添加一行：
  appServerPorts = 0
  保存，然后重启splunkd and splunkweb。或者splunk resatrt.
  ```

  然后启动服务下的splunkweb服务即可。

  ![](C:\Users\Administrator\Desktop\splunk-img\splunk安装\23.png)

  2、还有一种情况，splunk的web管理界面可能无法访问，就是默认的8000端口被占用。解决方案：

  ```shell
  C:\Program Files\Splunk\bin>splunk restart
  然后按照提示修改splunk的端口即可。
  ```


## Linux安装splunk

### 基于DEB包安装

该方式适用于Ubuntu/Debian系列操作系统

```shell
dpkg -i splunk-7.2.1-be11b2c46e23-linux-2.6-amd64.deb 
```

![](C:\Users\Administrator\Desktop\splunk-img\splunk安装\splunk-2.png)



### 基于源码包安装

该安装方式适用于Linux大多数发行版本：

```shell
#解压到/opt/目录
tar -zxvf splunk-7.2.1-be11b2c46e23-Linux-x86_64.tgz -C /opt/
#切换到/opt/bin
cd /opt/splunk/bin
```

### 基于RPM包安装

该安装方式适用于RHEL/Centos系列系统

```shell
#设置安装包为744权限（rwxr--r--）
chmod 744 splunk_package_name.rpm
#安装splunk默认安装目录为/opt/splunk
rpm -i splunk_package_name.rpm
#自定义splunk的安装目录
rpm -i --prefix=/opt/new_directory splunk_package_name.rpm
#启动splunk服务
./splunk start --accept-license
#启动程序加入启动项
./splunk enable boot-start 
```

## macOS 安装splunk

  双击DMG安装包，然后出现如下界面，然后双击`Install Splunk`开始下一步的安装。

![](C:\Users\Administrator\Desktop\splunk-img\splunk安装\splunk-9.png)

按照提示继续进入下一步。

![](C:\Users\Administrator\Desktop\splunk-img\splunk安装\splunk-10.png)

同意软件许可协议，进入下一步安装。

![](C:\Users\Administrator\Desktop\splunk-img\splunk安装\splunk-11.png)

![](C:\Users\Administrator\Desktop\splunk-img\splunk安装\splunk-12.png)

这一步我们可以自定义splunk的安装位置，也可以默认安装即可。

![](C:\Users\Administrator\Desktop\splunk-img\splunk安装\splunk-13.png)

等待少许时间即可完成splunk安装，成功页面的提示了splunk在macOS 下的两种启动方式。点击弹框中的“OK”，初始化splunk。

![](C:\Users\Administrator\Desktop\splunk-img\splunk安装\splunk-14.png)

设置splunk管理界面的登录账号和密码。

![](C:\Users\Administrator\Desktop\splunk-img\splunk安装\splunk-15.png)

选择 Start and Show Splunk，启动splunk。

![](C:\Users\Administrator\Desktop\splunk-img\splunk安装\splunk-16.png)

至此基于macOS 的splunk就完成了。

![](C:\Users\Administrator\Desktop\splunk-img\splunk安装\17.png)

### 使用操作

#### 启动splunk服务

- **基于Windows启动splunk**

  ```shell
  
  ```

- **基于Linux启动splunk**

splunk的文件解压到`/opt/splunk`。切换到`/opt/splunk/bin`下，运行如下命令启动splunk服务。

```shell
 #启动splunk服务
/opt/splunk/bin# ./splunk start 
#同意license
Do you agree with this license? [y/n]: y 
#设置splunk账户及密码，密码不少于8位。
Please enter an administrator username: admin	
Password must contain at least:
   * 8 total printable ASCII character(s).
Please enter a new password: 
Please confirm new password: 
```

服务器启动后，访问服务器的8000端口，使用设置的账户密码即可登录到WEB管理界面。

```shell
#本地WEB登录：
http://127.0.0.1:8000 or http://localhost:8000
#远程WEB登录：
http://IP:8000
```

![](C:\Users\Administrator\Desktop\splunk-img\splunk安装\splunk-3.png)

![](C:\Users\Administrator\Desktop\splunk-img\splunk安装\splunk-4.png)

- **基于macOS 启动splunk**

1、 点击桌面的Splunk图标，完成splunk服务的启动和连接。

2、在终端命令行下运行`$/Applications/Splunk/bin/splunk start`

#### 停止splunk服务

- **基于Windows停止splunk服务**

```shell
C:\Program Files\Splunk\bin>splunk stop
```

- **基于Linux停止splunk**

```shell
/opt/splunk/bin# ./splunk stop
```

- **基于macOS停止 splunk**

```shell
$/Applications/Splunk/bin/splunk stop
```



#### 重启splunk服务

- **基于Windows启动splunk**

```shell
C:\Program Files\Splunk\bin>splunk restart
```

- **基于Linux重启splunk**

```
/opt/splunk/bin# ./splunk restart
```

- **基于macOS重启splunk**

```
$/Applications/Splunk/bin/splunk restart
```
