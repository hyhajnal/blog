### 创建分支
``` bash
# 本地
git checkout -b feature/test

# 远程
git checkout -b feature/test origin/develop
```

### clone 指定分支
``` bash
git clone -b gh-pages https://github.com/hyhajnal/blog.git blog
```

### 删除分支

``` bash
# 删除本地
git branch -D fature/test

# 删除远程
git push origin --delete feature/test 或者 git push origin :feature/test
```

### 关联远程分支
``` bash
git branch --set-upstream-to origin/feature/test 或者 git branch -u origin/test

# 查看关联分支
git branch -vv
```

### gitignore已加入版本控制的文件
``` bash
git rm -r --cached .
```
再添加到.gitignore --> add --> push

### 全局配置
``` bash
# 查看全局配置
git config --list

# 更改全局配置
git config --global user.name "hajnal"
git config --global user.email hyhajnal@gmail.com

# 删除配置
git config --unset user.name
git config --unset user.email

# 避免 pull 的时候需要输入密码 
git config --global credential.helper store

# 删除密码 
git config --system --unset credential.helper

# 删除多个
warning: user.email has multiple values
git config --replace-all user.email hyhajnal@gmail.com

~/.gitconfig
~/.git-credentials
```

### 版本回退 revert & reset
``` bash
#选择撤回的版本号
git revert -n commit_id_start..commit_id_end(撤回到start的位置，生成多个commit)
git revert commit_id_start..commit_id_end(撤回到start的位置，需要手动提交，只会生成一个commit)
:q 退出即可

git reset --hard 7c62b6ad (只在本地用)
git reset --soft 7c62b6ad （回退到待git commit状态）
git reset --mixed 7c62b6ad（回退到待git add状态）
# 这里的版本号是指上一个版本号
```

### merge
```
git checkout master
git merge work
git merge origin/master  将origin的master分支merge到当前分支

# 退出当前 merge
git reset --hard HEAD
```

### rebase
``` bash
git checkout work
git rebase master
git rebase --continue / git rebase --skip
```

### submodule
``` bash
$ git submodule add https://github.com/hyhajnal/blog.git blog

# 会生成.gitmodule
```

### 合并多个commit
``` bash
git rebase -i --root
# 编辑commit前的 pick 为 s 
# 保存退出
```

### 只提交dist目录到远程gh-pages
``` bash
# 注意不要把dist放到gitignore里
git subtree push --prefix=dist origin gh-pages
```

### git commit 规范
* feat：新功能（feature）
* fix：修补bug
* docs：文档（documentation）
* style： 格式（不影响代码运行的变动）
* refactor：重构（即不是新增功能，也不是修改bug的代码变动）
* test：增加测试
* chore：构建过程或辅助工具的变动
