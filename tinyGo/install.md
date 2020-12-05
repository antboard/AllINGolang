# 安装

其实我好久之前就装过, 结果没安装成功。万事开头难，中间难，结尾难。 本来一个 brew install 就可以完成的事情。 卡住了， 报错了，歇菜了。

然后用 docker 方式安装， 太大了。 不好用，缺东西。 是不是很多人像我 一样，就这么卡住了？

时过很久， 今天按照 tinyGo 的方式， https://tinygo.org/getting-started/ 从主页的提示， 开始安装。 开了梯子。感觉似乎就顺利了很多。

```shell
brew install tinygo
Updating Homebrew...
^C
==> Installing tinygo from tinygo-org/tools
==> Downloading https://github.com/tinygo-org/tinygo/releases/download/v0.16.0/t
Already downloaded: /Users/icecut/Library/Caches/Homebrew/downloads/60c2490b4bb74c5a65c2998dcdd551b8e53dfae6c4aabaa3b03d29a4e06ba14d--tinygo0.16.0.darwin-amd64.tar.gz
/usr/local/Cellar/tinygo/0.16.0: 2,952 files, 351MB, built in 25 seconds
```

我这是 macos, 不同系统应该问题不大,都有自动安装工具. 

```shell
~ icecut$ tinygo version
tinygo version 0.16.0 darwin/amd64 (using go version go1.14 and LLVM version 10.0.1)
```
这就是安装成功了. 
我看了一下用 stm32的单片机, 还需要装一个 openocd, 但是, openocd 的网站上并没有说支持 stlink...这倒不是问题.
好的开始是成功的一半。