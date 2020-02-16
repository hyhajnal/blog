## npm 常用命令

``` bash
# 查看包的安装路径
npm root eslint-plugin-html
/Users/hajnal/WorkSpace/h5Edit/editor/client/node_modules

# 全局包安装路径
~ % npm root -g
/usr/local/lib/node_modules

# 重新指定安装路径
npm config set prefix /usr/local

# 查看全局安装了哪些包
npm list -g --depth=0

# 查看npm包的版本
npm list @skpm/builder
skytree@0.1.0 /Users/hajnal/skytree
└── @skpm/builder@0.5.10

# 查看npm包全局版本
npm list xxx -g

# 安装n工具
sudo npm install -g n

# 清除node.js的cache
sudo npm cache clean -f

# 安装稳定版
sudo n stable

# 更新npm到最新版
npm i -g npm

node -v
npm -v

# 更新 npm 包
npm install -g npm-check-updates


# 更新node版本
err: asyncWrite is not a function
sudo npm cache clean -f


# node 安装的目录
~ % where node
/Users/hajnal/.nvm/versions/node/v11.4.0/bin/node


#设置npm源
npm config set registry https://registry.npm.taobao.org
或者 nrm add taobao https://registry.npm.taobao.org
```



#### npm  发包

npm 版本号管理   X.Y.Z。不要手动修改package.json的内容，改用命令：

- 如果只是修复bug，需要更新Z位。
- 如果是新增了功能，但是向下兼容，需要更新Y位。
- 如果有大变动，向下不兼容，需要更新X位。

```bash
npm version patch # 升级修订号，例如：1.0.0 -> 1.0.1
npm version minor # 升级次版本号，例如：1.0.1 -> 1.1.0
npm version major # 升级主版本号，例如：1.1.1 -> 2.0.0
```



### scripts

`prepare`   在   `npm publish`  之前执行，可用于构建



#### npm包本地调试

* npm 包目录 `npm link`
* 项目目录 `npm link skytree-node`



#### yarn 优势 ?

Facebook发布的新一代包管理工具：快、可靠、安全，为了弥补npm的不足（不过 npm 5 以后功能提升不少）

* 速度快：并行安装包、支持离线安装
* 默认依赖锁定 yarn.lock（npm也有shrinkwrap）
* 命令语义化，输出简洁



#### nvm or n?

```bash
brew install nvm

# 安装完成后，必须在你的 .bash_profile 加入以下这行，让你可以直接在shell使用nvm指令
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh" # This loads nvm

export NVM_DIR="$HOME/.nvm"
  . "/usr/local/opt/nvm/nvm.sh"

$ source ~/.bash_profile
```

<img src="../assets/image-20181210185352335.png" alt="image-20181210185352335" style="zoom: 25%;" />