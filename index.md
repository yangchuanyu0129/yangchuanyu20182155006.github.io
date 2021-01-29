1）Repositories(仓库)项目代码托管功能
登录后点击右上角的加号(New project)。
Project path：如果你属于group的话可以选group名字，这样项目就会放在对应group下，一般团队项目比较好用。
Project name：你的项目名字
Import project from：可以从多个github、bitbucket等主流托管平台导入项目。
Project description：项目描述，可选
Visibility Level：项目可见级别
oPrivate：私有项目，需要授权才能访问，适合个人、团队开发。
oInternal：内部项目，注意只要登录账号就能访问，适合开源贡献代码。
oPublic：公开项目，不用登录就能访问，适合分享项目。
点击create，创建项目，进入空项目，会出现初始化步骤，可以用ssh和https方式来上传代码。
（2）版本管理功能
为规范源代码版本管理，现将各分支表述如下：
1.master分支
存放的应该是随时可供在生产环境中部署的代码
当开发活动告一段落，产生了一份新的可供部署的代码时，master分支上的代码会被更新。同时，每一次更新，都有对应的版本号标签（TAG）。
分支命名：master
该分支，由管理员负责维护，其它人只有拉取权限。来自于release分支的合并，供发版使用
生命周期：伴随着整个项目的生命周期，项目结束时结束。
2.develop分支
develop分支是每次迭代版本的共有开发分支，从最新的master分支派生（管理员操作）
当develop分支上的代码已实现了软件需求说明书中所有的功能，派生出release分支（管理员操作）
分支命名：dev-版本号
该分支，由开发人员在各自的feature分支开发完成后，合并至该分支。
生命周期：一个阶段功能开发开始到本阶段结束
3.release分支
从develop分支派生（管理员操作）
测试环境中出现的bug，统一在该分支下进行修改，并推送至远程分支。修改内容必须合并回develop分支和master分支。
分支命名惯例：release-版本号
生命周期：一个阶段功能开发结束开始，完成阶段功能测试并修复所有发现bug，合并会develop分支结束。
4.feature分支
在开发一项新的软件功能的时候使用，这个分支上的代码变更最终合并回develop分支
分支命名惯例：feature-姓名全拼-分支说明-日期 / feature-分支说明-日期
例：接到一个开发关于cc视频点播替换的任务，你需要从develop分支拉出一个分支，并命名为：release-yuruixin-ccVideo-20171117。然后在该分支下进行开发，开发结束，将该分支合并至develop分支（此时的代码必须为可运行的，不能影响到他人），合并完成删掉该特性分支。
开发人员的每一个新功能开发都应该在该类分支下进行。
生命周期：开发一个新功能开始，完成新功能开发并合并回develop分支结束。
5.hotfixes分支
在master分支发现bug时，在master的分支上派生出一个hotfixes分支，修改完成后，合并至master分支以及develop分支，合并完成，删除该hotfixes分支。
分支命名惯例：hotfixes-姓名全拼-分支说明-日期
示例：hotfixes-yuruixin-cclivebug-20171117
生命周期：发现master分支bug开始，完成master分支bug结束。

（3）代码查找功能
指定搜索方式
通过语言搜索代码
通过fork的数量或者是否有父节点的方式搜索
按照目录结构搜索
通过文件名搜索
根据扩展名来搜索代码
通过用户或者组织来查找
