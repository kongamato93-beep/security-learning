## 网络安全实验课笔记
#### 把用户移动到组内

usermod -aG 组名 用户名

-a append(追加)，如果没有就会把用户的原有的所有附属组列表换成新加组

useradd -g linuxgroup linux2

-g 是主组，-G 是附加组，每次useradd都需要指定主组不然就会加到默认组或者自动创建同名组
主组？文件默认归属

### cat /etc/passwd

举第一行root的例子说明：

Root:x:0:0:root:/root:/bin/bash

这一行的格式为：

用户名:密码:UID:GID:用户注释信息:用户家目录:Shell定义。

其中使用冒号隔开的每个部分分别代表：

用户名: 用户的名称。

密码: X表示占位符,也可以是密码。表示真正的密码哈希存在 /etc/shadow 里，这里只放一个 x。

UID: 用户识别代码。

GID: 用户所属组的GID(基本组)。

用户注释信息：Comment，可以完善用户的基本信息。

用户家目录，系统登录用户后的工作目录。

Shell：定义用户登录系统所使用的shell，指定的shell需要在/etc/shells中出现。

/etc/shadow：用户密码及其相关属性，可使用pwck命令校验格式无效用户等，用cat /etc/shadow查看该文件。


