# 一. github 创建。

1. git init ; 初始化库和创建库
2. git status;检查文件
3. git add . ;添加文件到库。
4. git status ;检查是否添加到库。变成绿色则成功。
5. git commit -m'';
6. git push ;上传到github上。
    报错情况：

      $ git push

       fatal: No configured push destination.
       Either specify the URL from the command-line or configure a remote repository using

          git remote add <name> <url>

       and then push using the remote name

          git push <name>
      上述错误代表远程端没有接口；需要在GitHub上建立一个新的项目。
      输入  git remote add origin (git@github.com:zhou1112/9-18.git)括号里是ssh地址
7. git push

      出现错误：

      $ git push
       fatal: The current branch master has no  upstream branch.
       To push the current branch and set the remote as upstream, use

          git push --set-upstream origin master
      输入  git push -u origin master。
8. git push

##  二. 修改GitHub文件
1. git status
2. git add .
3. git commit -m'remove'
4. git push

### 三.git部署

1. 编译一下;
  在webpack.config.js中 加:
    publicPath: "./build/",
2. 然后在git上运行 npm run build;运行之后情况：
          $ npm run build
          > 8-30-webpack@1.0.0 build E:\web前端\航宙\git\9-18
          > webpack --colors -p

  (注意package.json中
   "build": "node_modules/.bin/webpack --colors -p",)    
3. git diff 简单的看一下 修改了什么。

4. git checkout -b gh-pages；建立分支
  然后重新打开atom 同步分支

5. 删除多余的文件 然后推送分支；
  git push 之后

  $ git push

        fatal: The current branch gh-pages has no upstream branch.
        To push the current branch and set the remote as upstream, use

        git push --set-upstream origin gh-pages


6. git branch;查看分支
7. git checkout master;回到master分支(注：被删除文件会出现)

### 四. 文档修改后 重新部署
1. master 中先重新推送
2. 推送成功之后
          npm run build
   之后把build拿出来；

3. 进入gh-pages分支；把build替换。
4. 在分支中推送

### 五. 克隆github文档
1. 选择你需要克隆的项目；复制ssh地址：
  git clone + ssh地址
2. 删除 .git ：rm -rf .git;

3. npm i

4. 建库
