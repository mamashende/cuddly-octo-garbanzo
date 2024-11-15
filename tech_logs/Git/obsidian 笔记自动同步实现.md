#git学习
## ssh公钥生成及本地仓库与云端仓库的链接过程：  
[SSH 公钥设置 | Gitee 产品文档](https://help.gitee.com/base/account/SSH%E5%85%AC%E9%92%A5%E8%AE%BE%E7%BD%AE)  

## 链接相关示例代码：  
```bash
cd existing_git_repo
git remote add origin git@gitee.com:ouyang-zhiyong65532/test2.git
git push -u origin "master"```
```


## 同步简单示例  
upload.sh/bat  

```bash 
git status
git add .
git commit -m "automate update"
git push origin master

```  
download.sh/bat
```bash
git pull origin master
```

### 記得換新地方時先配置好git

```sh
git config --global user.email ouyangzhiyong0415@qq.com
git config --global user.name oyzy
```

## ==一个重要提醒：==
==请把 ./.obsidian/ 这个配置相关文件夹加入仓库的 .gitignore 文件，否则会因为不同设备上的obsidian配置不同（跟设备本身有关系造成的文件内容不同）产生无法解决的冲突

在同步obsidian仓库时，请注意在.gitignore中添加
```
*.json 
```
因为这是obsidian的所有本地配置文件，多端存在冲突风险
## 一个待解决的问题：
如果是git clong 下来的仓库，应该如何将其转移到我自己的私有仓库下进行同步呢？




### .gitignore文件无效问题解决
[浅析.gitignore文件不起作用的原因及其解决办法 - 古兰精 - 博客园 (cnblogs.com)](https://www.cnblogs.com/goloving/p/15017769.html)

[[2024-03-21]]
## 关于强制推送
```sh
git push -f
```
此命令会强制推送，无论是否存在冲突，问题是，它的推送机制相当于推送一个整体仓库的完全的备份，长期进行强制推送会导致仓库体积以非常快的速度膨胀，严重影响性能，可以适当进行GC工作

关于github上仓库大小的一个查询方式：
[查看github项目大小 - Borber - 博客园 (cnblogs.com)](https://www.cnblogs.com/borber/p/git_size.html)


[[2024-08-18]]目前仓库貌似自动推送出现了严重的问题，正在排查中

 来自另一台设备上的推送测试

再次测试

[[2024-08-28]]
测试