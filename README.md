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

## style-loader & css-loader - webpack的css样式加载模块
两者通常同时配置
- style-loader 把css文件中的样式添加到js文件中
- css-loader   在js文件中可以用`improt './mystyle.css'`的语法导入样式表

配置前先安装模块
```
yarn add --dev style-loader css-loader
```
webpack中配置style-loader和css-loader，style-loader在前，css-loader在后，顺序不能乱
```
module.exports = {
   ...
    module: {
        rules: [
            ...
            {
                test: /\.css$/,
                use: [
                    {
                        loader: "style-loader"
                    },
                    {
                        loader: "css-loader"
                    },
                ]
            }
        ]
    }
};
```

## css modules - css模块化的实践
css modules会自动把给对应的class添加上不同的名字，以防止css命名全局污染
css modules只能配置在css-loader中
```
module.exports = {
   ...
    module: {
        rules: [
            ...
            {
                test: /\.css$/,
                use: [
                    {
                        loader: "style-loader"
                    },
                    {
                        loader: "css-loader",
                        options: {
                            modules: true,                                     // 指定启用css modules
                            localIdentName: '[name]__[local]--[hash:base64:5]' // 指定css的类名格式
                        }
                    },
                ]
            }
        ]
    }
};
```
webpack中有一种更简洁的方式同时配置style-loader、css-loader、css modules的方式：
```
module.exports = {
   ...
    module: {
        rules: [
            ...
            {
                test: /\.css$/,
                loader: "style-loader!css-loader?modules"
            }
        ]
    }
};
```

## less - css的扩展语法，让css开发具备基本的逻辑编程能力
less工具是一个转换器，把less的语法转换成css标准语法，less文件后缀是`.less`

全局安装
```
yarn grobal add less
```
转换
```
lessc style.less > style.css
```
