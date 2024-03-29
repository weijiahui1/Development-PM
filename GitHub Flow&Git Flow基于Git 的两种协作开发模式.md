# 一、 GitHub Flow
    GitHub Flow —— 以部署为中心的开发模式,通过简单的功能和规则，持续且高速 安全地进行部署。
    在实际开发中往往一天之内会实施几十次部署，而支撑这一切的，就是足够简单的开发流程以及完全的自动化。
### 1.GitHub Flow 特点：
    1）令master 分支时常保持可以部署的状态
    2）进行新的作业时要从master 分支创建新的分支，新分支名称要具有描述性
    3）在2新建的本地仓库分支中进行提交
    4）在Github 端仓库创建同名分支，定期push
    5）需要帮助、反馈，或者branch已经准备merging时，创建Pull Request，以Pull Request 进行交流
    6）让其他开发者进行审查，确认作业完成后与master分支进行合并（合并的代码一定要测试
    7）与master分支合并后，立刻部署
### 2.使用Github Flow 的前提条件：
        1）团队规模最好控制在15-20人之内，具体见 how-github-works
        2）部署作业完全自动化。必须自动化，一天之类需要多次部署
        使用部署工具（Capistrano，Mina，Fabric,Webistrano,Strano等），让部署时所需的一系列流程自动化。
        通过Web界面进行部署，Capistrano 等部署工具需要命令执行操作，开发者以外的人很难实施部署
            Capistrano http://github.com/capistrano/capistrano //Ruby开发的代表性部署工具
            Webistrano http://kentaro/webistrano //可以通过Web执行Capistrano的工具
        导入开发时注意事项：随着团队人数的增多及成熟度的提高，开发速度会越来越快。
        往往一个部署尚未完成，另一名开发者就已经处理完下一个pull request，开始实施下一个部署。
        在这种情况下，一旦正式环境出现问题，很难分辨哪个部署造成了影响。为了应对该情况，建议在部署实施过程中通过工具加锁。
        Git Hook 自动部署

        3）重视测试
        让测试自动化
        编写测试代码，通过全部测试
        维护测试代码
# 二、Git Flow
### 1.Git Flow流程常用分支
* master
* develop
* feature
* release
* hotfix
### 2.Git Flow分支命名规范
    master（主分支，永远是可用的稳定版本，不能直接在该分支上开发）
    develop（开发主分支，所有新功能以这个分支来创建自己的开发分支，该分支只做只合并操作，不能直接在该分支上开发）
    feature-xxx（功能开发分支，在develop上创建分支，以自己开发功能模块命名，功能测试正常后合并到develop分支）
    feature-xxx-fix(功能bug修复分支，feature分支合并之后发现bug，在develop上创建分支修复，之后合并回develop分支。
            PS:feature分支在申请合并之后，未合并之前还是可以提交代码的，所以feature在合并之前还可以在原分支上继续修复bug)
    hotfix-xxx（紧急bug修改分支，在master分支上创建，修复完成后合并到 master）
### 3.Git Flow提交记录规范
    每个 git commit 记录都需要按照固定格式，具体格式为：
    第一行：作者: 功能模块名称（或 功能模块ID）
    第二行：提交描述，中英文皆可
      + ：增加代码
      *  ：修改代码
      -  ： 删除代码

### 4.图
![baidu-images](https://images2015.cnblogs.com/blog/718344/201609/718344-20160913141526648-581574208.png)
