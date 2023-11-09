#git常用指令

    git init 
    git branch -a //查看所有分支
    git checkout -b develop //切换到develop分支
    git remote -v  //查看分支远程地址
    git status //查看仓库状态

##配置个人账户和公司的SSH
###step1 
使用

    git config --local user.name "xxx"
    git config --local user.email "xx@xx.com"
    git config --global user.name "xxx"
    git config --global user.email "xx@xx.com"
配置全局用户名邮箱和本地用户名和邮箱，建议公司项目用本地配置公司的邮箱和姓名

###step2 
生成不同的密钥文件
ssh-keygen -t rsa -C "youemail"

###step3
配置不同网站用不同的ssh，在c:/user/xx/.ssh路径下新建config文件，文件中加如下配置

    #github配置
    Host github.com
    User youemai1
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/yoursaname1
    
    #公司gitlab配置
    Host xxxx #这里需要把网站改成你使用的网站，如：github.com
    User youemai2
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/yoursaname2

###step4
用文本编辑器打开生成的密钥文件中的.pub后缀文件，将其中内容添加到对应网站的ssh公钥