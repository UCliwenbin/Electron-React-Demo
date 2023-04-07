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

   