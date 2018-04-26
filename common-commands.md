## 用户相关

### 查看系统所有用户
1. 查看/home目录 

### 新增用户adduser
> adduser wukj

### 给新增用户设置密码
> passwd wukj mypassword

## 用户组相关

### 查看系统有哪些用户组
> cat /etc/group

### 新增用户组
> groupadd developer

可以通过cat /etc/group查看，已经添加的新用户组出现在文件中了

### 把刚新增的wukj用户添加到developer用户组
> sudo usermod -aG developer wukj

### 管理用户组（group）的工具或命令

```
groupadd  注：添加用户组；
groupdel         注：删除用户组；
groupmod        注：修改用户组信息
groups     注：显示用户所属的用户组
grpck
grpconv   注：通过/etc/group和/etc/gshadow 的文件内容来同步或创建/etc/gshadow ，如果/etc/gshadow 不存在则创建；
grpunconv   注：通过/etc/group 和/etc/gshadow 文件内容来同步或创建/etc/group ，然后删除gshadow文件；
```

### 给用户wukj和用户组developer添加sudo权限
修改/etc/sudoers文件
在文件末尾加上
```
wukj ALL=(ALL) NOPASSWD: ALL
%developer   ALL=(ALL)  NOPASSWD: ALL
```
