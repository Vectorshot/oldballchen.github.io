---
layout:		post
title:		创建Amazon EC2 instance 利用sftp传输本地文件 
subtitle:		DSCI551 Lab1
date:		2020-09-25
author:		OB
header-img: img/bgimg6.jpg
catalog: true
tags:
	- server
	- EC2
	- Linux
---



#### 1.选中EC2服务

![image-20200902224341187](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\image-20200902224341187.png)

#### 2.选中Launch Instance

![image-20200902224441032](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\image-20200902224441032.png)

#### 3.选择AMI

![image-20200902224547759](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\image-20200902224547759.png)

Amazon Linux AMI

#### 4.选择Instance类型

![image-20200902224740303](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\image-20200902224740303.png)

选择t2.micro，然后点击Review and Launch

#### 5.点击Launch

![image-20200902225011496](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\image-20200902225011496.png)

#### 6.创建key pair

![image-20200902225049720](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\image-20200902225049720.png)

点击Launch后会出现这个界面，选择create a new key pair，然后保存key pair到本地

![image-20200902225209607](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\image-20200902225209607.png)

点击download key pair

![image-20200902225336795](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\image-20200902225336795.png)

点击Launch Instances

![image-20200902225411729](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\image-20200902225411729.png)

![image-20200902225441088](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\image-20200902225441088.png)

点击View Instances

![image-20200902225547654](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\image-20200902225547654.png)

#### 7.查看Instance Information

![image-20200902225653077](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\image-20200902225653077.png)

#### 8.Instance操作

![image-20200902225911467](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\image-20200902225911467.png)

#### 9.连接Instance

​	![image-20200902230005617](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\image-20200902230005617.png)

#### 10.Cygwin连接Instance

##### 1.进入pem所在文件夹

![image-20200902230200673](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\image-20200902230200673.png)

##### 2.查看文件权限

![image-20200902230252163](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\image-20200902230252163.png)

##### 3.不改变文件权限

![image-20200902230527578](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\image-20200902230527578.png)

显示bad permissions

##### 4.修改权限

![image-20200902230732616](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\image-20200902230732616.png)

##### 5.连接Instance

![image-20200902230826205](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\image-20200902230826205.png)

ec2-user为默认用户

ssh -i "dsci551_fa20.pem" ec2-user@[dns ip]

直接复制的是dns ip，没有ec2-user

@后为dns ip

![image-20200902230919584](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\image-20200902230919584.png)

##### 6.在ec2 Instance上的home文件夹创建一个新文件夹

![image-20200902231151342](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\image-20200902231151342.png)

##### 7.在pem所在文件夹创建需上传文件

![image-20200902231301004](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\image-20200902231301004.png)

##### 8.退出登录

![image-20200902231542786](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\image-20200902231542786.png)

退出登录后才能把文件传输到Instance

##### 9.建立sftp连接

![image-20200902233233504](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\image-20200902233233504.png)

上传文件

##### 10.重新连接到Instance

exit退出sftp，再重复操作连接到Instance

![image-20200902233530291](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\image-20200902233530291.png)

##### 11.展示上传文件

![image-20200902233631392](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\image-20200902233631392.png)

##### 附录

安装Cygwin时，要选择openssh

![image-20200902234010829](C:\Users\11849\AppData\Roaming\Typora\typora-user-images\image-20200902234010829.png)

#### 参考链接

[ssh](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html)

[Putty](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/putty.html?icmpid=docs_ec2_console#putty-private-key)

[Information](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/connection-prereqs.html#connection-prereqs-get-info-about-instance)

[Information_account](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/managing-users.html)

[blog](https://kb.iu.edu/d/akqg)

[reference](https://www.digitalocean.com/community/tutorials/how-to-use-sftp-to-securely-transfer-files-with-a-remote-server)