---
title: SSH配置和密钥管理
date: 2020-10-20 15:29:21
tags:
categories:
---
### 检查存在的SSH key
```
ls -al ~/.ssh
```

### 生成新的SSH key
粘贴以下文本到命令行，把email地址替换成自己到地址，或任意标签。
```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
提示选择key的保存位置时，按确认键。
```
> Enter a file in which to save the key (/Users/you/.ssh/id_rsa): [Press enter]
```
按照提示设置密码即可。
```
> Enter passphrase (empty for no passphrase): [Type a passphrase]
> Enter same passphrase again: [Type passphrase again]
```
### 设置或修改密码,需要输入指定的私钥文件名
```
$ ssh-keygen -p
# Start the SSH key creation process
> Enter file in which the key is (/Users/you/.ssh/id_rsa): [Hit enter]
> Key has comment '/Users/you/.ssh/id_rsa'
> Enter new passphrase (empty for no passphrase): [Type new passphrase]
> Enter same passphrase again: [One more time for luck]
> Your identification has been saved with the new passphrase.
```
第一次使用sshkey会提示你输出密码，如果你选择保存在keychain中，则不用再输了。
如果没有保存，你也可以事后在添加SSHkey到ssh-agent的时候保存。
### 添加SSH key 到 SSH-agent
1.首先后台启动ssh-agent
```
$ eval "$(ssh-agent -s)"
```
2.修改config文件
- 检查是否存在该文件
```
$ open ~/.ssh/config
> The file /Users/you/.ssh/config does not exist.
```
- 如果不存在则要创建一个config文件
```
$ touch ~/.ssh/config
```
- 修改config文件，替换id_rsa为你要添加的key
```
Host *
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_rsa
```
3.用mac自带的ssh-add工具添加你的SSH 私钥并且保存密码在keychain中,把id_rsa替换为你要添加的key
```
$ ssh-add -K ~/.ssh/id_rsa
```
注： -K选项，是mac标准自带的，可以在添加SSHkey到 ssh-agent时，保存密码到keychain中。man ssh-add 可以查看ssh-add命令到详细用法。·


### 检查SSH连接是否建立
```
··
```
