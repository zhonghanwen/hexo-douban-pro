# hexo-douban-pro

一个在 [Hexo](https://hexo.io) 页面中嵌入豆瓣个人主页的小插件.

[![npm](https://img.shields.io/npm/v/npm.svg)](https://nodejs.org/en/)
[![Coverage Status](https://coveralls.io/repos/github/mythsman/hexo-douban/badge.svg?branch=master)](https://coveralls.io/github/mythsman/hexo-douban?branch=master)
[![NPM version](https://badge.fury.io/js/hexo-douban.svg)](https://www.npmjs.com/package/hexo-douban)
[![npm](https://img.shields.io/npm/dt/hexo-douban.svg)](https://www.npmjs.com/package/hexo-douban)
[![GitHub license](https://img.shields.io/github/license/mythsman/hexo-douban.svg)](https://github.com/mythsman/hexo-douban/blob/master/LICENSE)

[![NPM](https://nodei.co/npm/hexo-douban-pro.png)](https://nodei.co/npm/hexo-douban-pro/)

## 环境要求
* Node版本不大于10，否则会爬取不了数据。
* Node版本不大于10，否则会爬取不了数据。
* Node版本不大于10，否则会爬取不了数据。

使用vercel + Hexo的话，在vercel设置选择中找到Node版本选择10即可。

## 安装

``` bash
$ npm install hexo-douban-pro --save
```

## 配置

将下面的配置写入站点的配置文件 `_config.yml` 里(不是主题的配置文件).

``` yaml
douban:
  user: mythsman
  builtin: false
  book:
    title: 'This is my book title'
    quote: 'This is my book quote'
  movie:
    title: 'This is my movie title'
    quote: 'This is my movie quote'
  game:
    title: 'This is my game title'
    quote: 'This is my game quote'
  music:
    title: 'This is my music title'
    quote: 'This is my music quote'
  timeout: 10000 
```

- **user**: 你的豆瓣ID.打开豆瓣，登入账户，然后在右上角点击 "个人主页" ，这时候地址栏的URL大概是这样："https://www.douban.com/people/xxxxxx/" ，其中的"xxxxxx"就是你的个人ID了。
- **builtin**: 是否将生成页面的功能嵌入`hexo s`和`hexo g`中，默认是`false`,另一可选项为`true`(1.x.x版本新增配置项)。
- **title**: 该页面的标题.
- **quote**: 写在页面开头的一段话,支持html语法.
- **timeout**: 爬取数据的超时时间，默认是 10000ms ,如果在使用时发现报了超时的错(ETIMEOUT)可以把这个数据设置的大一点。

如果只想显示某一个页面(比如movie)，那就把其他的配置项注释掉即可。

## 使用
### 1.x.x版本

在1.x.x版本中，使用`hexo douban`命令即可生成指定页面，如果不加参数，那么默认参数为`-bgmi`。

**需要注意的是**，通常大家都喜欢用`hexo d`来作为`hexo deploy`命令的简化，但是当安装了`hexo douban`之后，就不能用`hexo d`了，因为`hexo douban`跟`hexo deploy`的前缀都是`hexo d`。

```
$ hexo douban -h
Usage: hexo douban

Description:
Generate pages from douban

Options:
  -b, --books   Generate douban books only
  -g, --games   Generate douban games only
  -m, --movies  Generate douban movies only
  -i, --musics  Generate douban musics only
```

如果配置了`builtin`参数为`true`，那么除了可以使用`hexo douban`命令之外，`hexo g`或`hexo s`也内嵌了生成页面的功能。


## 升级
我会不定期更新一些功能或者修改一些Bug，所以如果想使用最新的特性，可以用下面的方法来更新:

1. 修改package.json内hexo-douban的版本号至最新
2. 重新安装最新版本`npm install hexo-douban-pro --save`

或者使用`npm install hexo-douban-pro --update --save`直接更新。

## 显示
如果上面的配置和操作都没问题，就可以在生成站点之后打开 `//yourblog/books` 和 `//yourblog/movies`, `//yourblog/games`, 来查看结果.

## 菜单
如果上面的显示没有问题就可以在主题的配置文件 `_config.yml` 里添加如下配置来为这些页面添加菜单链接.
```yaml
menu:
  Home: /
  Archives: /archives
  books: /books     #This is your books page
  movies: /movies   #This is your movies page
  games: /games   #This is your games page
  musics: /musics   #This is your games page
```


## 截图
我们在下面这些常见的主题里测试了插件的使用效果:

### hexo-theme-landscape
![landscape](screenshot/landscape.png)

### hexo-theme-next
![next](screenshot/next.png)

### hexo-theme-yilia
![yilia](screenshot/yilia.png)

### hexo-theme-indigo
![indigo](screenshot/indigo.png)

### hexo-theme-aath
![aath](screenshot/aath.png)


## FeedBack
如果大家在使用的过程中有什么问题或者意见，欢迎随时提issue。

## Lisense
MIT
