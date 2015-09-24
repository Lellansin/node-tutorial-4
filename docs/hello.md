# 第一节 hello world

## 环境配置

node.js 的官网地址是：http://nodejs.org/

一般来说根据你的操作系统不同，打开就会看到不同系统的下载安装包。

### Windows

不会配置的推荐使用  msi 文件安装，在 Downloads（下载）页面中可以找到。 `Windows Installer (.msi)` 下载之后点击安装，一路确定就可以自动安装并把相关的exe目录写到系统环境变量，并且集成npm。

如果懂得配置环境变量之类的也可以自行下载 `Windows Binary (.exe)` 来安装。

安装完毕后打开 CMD，运行 `node -v` 有结果表示成功

### Linux

简单的说：

在 ubuntu 上可以使用 `sudo apt-get install nodejs` 来自动安装。
在 centos 上可以使用 `sudo yum install npm` 来自动安装。

如果无法自动安装简易在 https://nodejs.org/en/download/ 中下载 ` Linux Binaries (.tar.gz)` 通过 `tar zxvf` 解压之后加入到系统环境变量中使用。

安装完毕之后打开 terminal 运行 `node -v` 有结果表示成功

### Mac

可以通过 `brew install nodejs` 来自动安装

或者还可以在 https://nodejs.org/en/download/ 中下载 `Mac OS X Installer (.pkg)` 来双击安装，这个 pkg 可以自动加入环境变量等。

除此之外之外还可以下载 `Mac OS X Binaries (.tar.gz)` 通过 `tar zxvf` 解压之后加入到系统环境变量中使用。

安装完毕之后打开 terminal 运行 `node -v` 有结果表示成功

## Hello world

新建一个 hi.js 文件文件，输入：
```javascript
console.log('hello world');
```
保存好了之后 cd 到该文件所在目录运行
```
node hi.js
```
看到输出的 `hello world` 即为成功。


下一节 [第二节 数值](https://github.com/Lellansin/node-tutorial-4/blob/master/docs/value.md)
