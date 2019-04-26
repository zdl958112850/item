# git的简单操作

- git init  git的初试化
- git add 文件名
- git commit  -m   "message说明" 
- git status  用来查看当前代码有没有被放到仓库里面去
- git add ./    就是把里面所有修改的文件添加到大门口

### 直接放到仓库里面

可以一次性把修改过的代码放到房间里,不用再写add  ,  git commit --all -m  "这是一次性操作"

- git  log  可以查看提交的记录
- git log --oneline 简写,看到简洁版的
- git reset --hard Head~0 表示回到最后一次上次,后面要是填1的话表示回到上上一次上传的时候
  - 可以通过版本号来进行代码的回退
  - git reset --hard ca3cc90将代码号写后面即可
  - 也可以通过这种方法回到以前的
  - git reflog  可以把每次版本切换的记录展示
- git branch zdl  创建zdl分支  使用 git branch查看  刚创建的时候和master的内容是一样的
- 切换分支: git checkout dev  切换到 dev分支
  - Switched to branch  'master'切换到主分支
- 将分支合并到主分支 
  - git merge zdl  将zdl分支合并到master主分支,把当前分支和指定分支进行合并,当前分支就是git branch命令输出带星号的分支
- 使用 git branch -d dev 将dev分支删除掉,但是不能再dev分支里面写

### 合并分支

- 若遇见冲突将手动的去处理

### 拉去数据

- 使用git  pull 地址 , 在这一步之前要初始化使用git init初始化
- ① git pull [地址]   分支名可以不用写
- ② 通过克隆的方式  git clone 地址
  - 注意:使用克隆一般是第一次
  - pull如果相同的话,合并

### 上传方式

- 使用ssh方式上传代码
  - 公钥 私钥,两者有关联
  - 生成公钥,和私钥
    - 公钥  ssh-keygen -t rsa -C "任意邮箱"  注册公钥,然后去你注册的文件目录下找到id_rsa.pub,打开复制,然后再去github里面的设置里面ssh添加公钥
- 先pull,然后看看有没有错,然后再把冲突解决

### 解决多次写地址的烦恼

- git remote add origin  地址   将地址放在一个变量origin 里面
- git push origin master 后面的master 表示提交到服务器的master分支
- 里面若写有  -u  以后就不必写master了和地址  直接写 git push就能上传