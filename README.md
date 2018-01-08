# Note-React-Utilities
React技术栈工具

## npm - 包管理工具(Node Package Manager)
这个本来是Node.js的包管理工具，所以要用这个工具，就到Node.js官网安装Node.js环境，就带有npm工具
```
https://nodejs.org/zh-cn
```

## yarn - 包管理工具
也是基于Node.js实现的，效率比npm高。

brew安装，但是这种方式会更新node到最新版本
```
brew install yarn
```
npm安装
```
npm install -g yarn
```

## create-react-app - 官方React项目创建工具
用于快速创建React的Hello World程序
1. 安装
```
sudo npm install -g create-react-app
```
2. 创建项目
```
create-react-app <project name>
```
3. 常见TypeScript的React项目
```
create-react-app <project name> --scripts-version=react-scripts-ts
```
4. 编译并运行项目
```
cd <project name>
npm satrt
```

## dva - 阿里出品的React + Redux 的项目架构
用于快速创建React + Redux的项目
1. 安装
```
sudo npm install -g dva-cli
```
2. 创建项目
```
dva new <project name>
```
3. 编译并运行项目
```
cd <project name>
npm satrt
```

## webpack - 前端强大打包工具，可以把项目中不同的模块和包，统一打包成浏览器支持的js代码
1. 安装
```
npm install --save-dev webpack
```
或
```
yarn add --dev webpack
```

## babel - js代码编译器，会把ES5、ES6的代码转化为ES代码，以兼容不同的浏览器
在webpack中，可以使用babel-loader来处理js和jsx文件，以兼容浏览器

要在webpack配置babel-loader需要安装模块
```
yarn add --dev babel-core babel-loader babel-preset-env
```
要想babel-loader处理react文件，需要安装对应的babel模块
```
yarn add --dev babel-preset-react
```

