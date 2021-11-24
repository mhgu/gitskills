# Git 环境
## 1、默认选项安装

## 2、Git配置用户
安装完成后打开C:\Program Files\Git\git-bash.exe
- 或者 右键-> Git Bash Here

 git config --global user.name "[name]”
 git config --global user.email "[email address]" 

```
mhgu@yhpc MINGW64 ~
$ git config --global user.name "mhgu"

mhgu@yhpc MINGW64 ~
$ git config --global user.email "mhgu2012@yahoo.com"
``` 
 
## 3、Git生成密钥 
执行ssh-keygen命令，根据提示一步步执行

```
mhgu@yhpc MINGW64 ~
$ ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/c/Users/mhgu2/.ssh/id_rsa):
Created directory '/c/Users/mhgu2/.ssh'.
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /c/Users/mhgu2/.ssh/id_rsa
Your public key has been saved in /c/Users/mhgu2/.ssh/id_rsa.pub
The key fingerprint is:
SHA256:+vY6Swopqyi+EzDPwfpe/5np7ow+msrMseHREmD4JGM mhgu@yhpc
The key's randomart image is:
+---[RSA 3072]----+
|                 |
|.                |
|=E.              |
|=*o              |
|.=o.    S        |
|..oo . .         |
| .B = . .        |
|o*.X +.*o+       |
|==%.oo=B&=.      |
+----[SHA256]-----+

mhgu@yhpc MINGW64 ~
```

## 4、默认会在当前用户目录下创建.ssh文件夹

```
mhgu@yhpc MINGW64 ~/.ssh
$ ls -l
total 5
-rw-r--r-- 1 mhgu 197121 2590 Nov 19 16:00 id_rsa
-rw-r--r-- 1 mhgu 197121  563 Nov 19 16:00 id_rsa.pub

```
id_rsa -> 私钥文件
id_rsa.pub -> 公钥文件


## 5、github 上设置 SSH公钥
登录github 账号，转到个人设置页面。
https://github.com/settings/profile
-> SSH and GPG keys -> new SSH key

title：mhg@yhpc
content: 将 id_rsa.pub 的内容添加到 页面中

## 6、pull 代码
复制需要拉取项目的ssh 地址，然后 在本地目录使用 git clone
创建代码仓。
```
mhgu@yhpc MINGW64 /e/github
$ git clone git@github.com:mhgu/gitskills.git
Cloning into 'gitskills'...
The authenticity of host 'github.com (20.205.243.166)' can't be established.
ED25519 key fingerprint is SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? y
Please type 'yes', 'no' or the fingerprint: yes
Warning: Permanently added 'github.com' (ED25519) to the list of known hosts.
remote: Enumerating objects: 19, done.
remote: Total 19 (delta 0), reused 0 (delta 0), pack-reused 19
Receiving objects: 100% (19/19), 4.64 KiB | 1.55 MiB/s, done.
Resolving deltas: 100% (6/6), done.

mhgu@yhpc MINGW64 /e/github
$

```