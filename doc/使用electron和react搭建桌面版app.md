# 使用Electron和React搭建桌面app

搭建过程主要是：参考文档：https://blog.csdn.net/double_sweet1/article/details/124445859，步骤如下：

1. 创建一个React项目
2. 在React的Demo项目中引入Electron
3. 打包Electron为桌面执行文件
4. 打包优化
5. 源码加密
6. 测试

## 1.创建一个React项目

1. 使用create-react-app快速生成一个react的Demo，react2electron为项目名称

```perl6
npx create-react-app react2electron
```

 2. 运行npm start,浏览器中看到如下界面代表搭建React初始项目成功！：	

    <img src="https://img-blog.csdnimg.cn/img_convert/64423da4dd8a616bb9ef191143fe9184.png" alt="img" style="zoom:50%;" />

## 2.在React的Demo项目中引入Electron

​	安装electron框架到工程中；这里使用`yarn `工具，具体区别可以查看这篇文章[npm，cnpm，yarn，pnmp之间的区别](https://blog.csdn.net/qq_68086484/article/details/127235359)。因为`yarn`使用官方源会比较慢，所以这里需要更新为国内的镜像源，具体可以查看：[1.yarn切换源地址](https://blog.csdn.net/lisili1993/article/details/106012542)、[yarn安装依赖速度太慢的解决办法](https://blog.csdn.net/sg_knight/article/details/127048097)。

1. 执行Electron的安装命令：

```shell
yarn install electron --save-dev
```

2. 在项目根目录下新增main.js文件

   main.js是React集成Electron的关键文件,具体代码：https://github.com/UCliwenbin/Electron-React-Demo/blob/main/src/main.js

3. 修改项目的package.json
   + homepage属性
   + 新增main属性
   + 在scripts里新增脚本启动命令

​	具体配置看代码：https://github.com/UCliwenbin/Electron-React-Demo/blob/main/package.json

## 3.打包Electron为桌面执行文件

​	这里打包使用的是官方推荐的`electron-forge`,具体使用可以参考以下文档：

1. https://www.electronforge.io/
2. [electron-forge打包教程](https://www.wangt.cc/2021/07/electron%E6%95%99%E7%A8%8B%EF%BC%883%EF%BC%89%E5%A6%82%E4%BD%95%E6%89%93%E5%8C%85-electron-%E7%A8%8B%E5%BA%8F%EF%BC%9Aelectron-forge-%E7%9A%84%E4%BD%BF%E7%94%A8%E6%95%99%E7%A8%8B/)

​	直接使用`electron-forge`脚手架工具来进行创建App，相关脚手架工具：

```shell
# 执行脚手架工具
yarn create electron-app my-app

# 执行app
cd my-app
yarn start

```

​	具体配置可以查看：https://github.com/UCliwenbin/Electron-React-Demo/blob/main/package.json

​	文档中使用了[electron-packager](https://www.npmjs.com/package/electron-packager)工具进行打包,这个我没有用，所以不太确定是否好用。