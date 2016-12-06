---
layout: post
title: "iTerm2 和 oh my zsh设置DIY"
date: 2016-12-06 
description: "修改iTerm2的style"
tag: 博客 
---   

　　iTerm2是非常好用的,要必须mac系统自带的终端好用的多,而且还能自己修改主题,让编写更清晰.


## DIY过程     

### 首先下载iTerm2         


下载地址：[http://www.iterm2.com](url)


打开iTerm2

### 安装oh-my-zsh

```
curl -L https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh | sh
```

### 安装Poweline

在官网有教程，我们只需要执行官网第一条安装指令就行

如果你的终端能够正常执行pip指令，那么直接执行下面的指令可以完成安装     

```
pip install powerline-status
```

如果没有，则先执行安装pip指令

```
sudo easy_install pip
```

## 下载,安装字体库


下载地址：[https://github.com/powerline/fonts](url)


### 将工程下载下来后cd到install.sh文件所在目录

### 执行指令安装字体库

执行./install.sh指令安装所有Powerline字体

安装完成后提示所有字体均已下载到/Users/wangjinbao/Library/Fonts路径下

```
All Powerline fonts installed to /Users/wangjinbao/Library/Fonts
```

## 设置iTerm 2的Regular Font 和 Non-ASCII Font

安装完字体库之后，把iTerm 2的设置里的Profile中的Text 选项卡中里的Regular Font和Non-ASCII Font的字体都设置成 Powerline的字体，我这里设置的字体是12pt Meslo LG S DZ Regular for Powerline

![](/images/posts/iTerm2/设置iTerm2.png)

## 配色方案

### 安装配色方案

进入刚刚下载的工程的```solarized/iterm2-colors-solarized``` 下双击``` Solarized Dark.itermcolors``` 和 ```Solarized Light.itermcolors``` 两个文件就可以把配置文件导入到 iTerm2 里

### 配置配色方案

通过load presets选择刚刚安装的配色主题即可

![](/images/posts/iTerm2/配色方案.png)

## 使用agnoster主题

### 下载agnoster主题
到下载的工程里面运行install文件,主题将安装到```~/.oh-my-zsh/themes```目录下

### 设置该主题
进入~/.zshrc打开.zshrc文件，然后将ZSH_THEME后面的字段改为agnoster。ZSH_THEME="agnoster"（agnoster即为要设置的主题）


### 增加指令高亮效果——zsh-syntax-highlighting

指令高亮效果作用是当用户输入正确命令时指令会绿色高亮，错误时命令红色高亮

## cd到.zshrc所在目录

## 执行指令将工程克隆到当前目录

```
git clone git://github.com/zsh-users/zsh-syntax-highlighting.git
```

## 打开.zshrc文件，在最后添加下面内容

```
source XXX/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
```

保存文件。

注意：xxx代表.zshrc所在目录

### cd ~/.oh-my-zsh/custom/plugins

### 再次打开.zshrc文件，在最后面添加下面内容

```
plugins=(zsh-syntax-highlighting)
```

保存文件。


文／SuperDanny（简书作者）

转载地址[http://www.jianshu.com/p/7de00c73a2bb](url) 谢谢！
