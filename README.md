# Hexo主题--bamboo介绍
这是一个基于Hexo的响应式博客主题，[演示示例](https://yuang01.github.io/)
<!-- more -->
## 下载
首先你需要有一个[Hexo](https://hexo.io/zh-cn/)，按照官网的方法，很容易的就能创建一个hexo博客。
当你有了hexo博客之后，进入`themes`文件夹下使用 `Git clone` 命令来下载:
``` bash
git clone https://github.com/yuang01/hexo-theme-bamboo.git
```
## 配置
### 切换主题

修改 Hexo 根目录下的 `_config.yml` 的  `theme` 的值：`theme: hexo-theme-bamboo`

#### `_config.yml` 文件的其它修改建议:
 
- 请修改 `_config.yml` 的 `url` 的值为你的网站主 `URL`（如：`http://xxx.github.io`）。`author`值改为你的名称（如：yuang），`description`值随便写一段描述（如：千磨万击还坚劲，任尔东西南北风）
- 如果你是中文用户，则建议修改 `language` 的值为 `zh-CN`。

### 代码高亮
这个主题采用的是[hexo-prism-plugin](https://github.com/ele828/hexo-prism-plugin)这个Hexo插件来做代码高亮，安装命令如下：
```bash
npm i -S hexo-prism-plugin
```
然后，修改 Hexo 根目录下 `_config.yml` 文件中 `highlight.enable` 的值为 `false`，并新增 `prism` 插件相关的配置，主要配置如下：

```yaml
highlight:
  enable: false

prism_plugin:
  mode: 'preprocess'    # realtime/preprocess
  theme: 'tomorrow'    # 这里可以选择不同样式的主题
  line_number: false    # default false
  custom_css:
```

### 搜索
本主题中还使用到了 [hexo-generator-search](https://github.com/wzpan/hexo-generator-search) 的 Hexo 插件来做内容搜索，安装命令如下：
```bash
npm install hexo-generator-search --save
```

在 Hexo 根目录下的 `_config.yml` 文件中，新增以下的配置项：

```yaml
search:
  path: search.xml
  field: post
```
在主题文件夹下的`_config.yml`文件中设置`search`为true或者false控制显示隐藏

### 新建分类 categories 页
`categories` 页是用来展示所有分类的页面，也就是导航上的分类页面，如果在你的博客 `source` 目录下还没有 `categories/index.md` 文件，那么你就需要手动或者使用命令新建一个，命令如下：
```bash
hexo new page "categories"
```
编辑你刚刚新建的页面文件 `/source/categories/index.md`，至少需要以下内容：
```yaml
---
title: categories
date: 2020-09-14 15:30:30
type: "categories"
layout: "categories"
---
```
### 新建标签 tags 页
`tags` 页是用来展示所有标签的页面，如果在你的博客 `source` 目录下还没有 `tags/index.md` 文件，那么你就需要新建一个，命令如下：
```bash
hexo new page "tags"
```

编辑你刚刚新建的页面文件 `/source/tags/index.md`，至少需要以下内容：

```yaml
---
title: tags
date: 2020-09-14 15:30:30
type: "tags"
layout: "tags"
---
```

### 新建关于我 about 页
`about` 页是用来展示**关于我和我的博客**信息的页面，如果在你的博客 `source` 目录下还没有 `about/index.md` 文件，那么你就需要新建一个，命令如下：

```bash
hexo new page "about"
```
然后可以在本主题下的`_config.yml`文件下，编辑以下字段进行关于我页面信息的更改
``` yaml
baseInfo # 基本信息，包括年龄，性别，坐标，状态
skills   # 技能
socialAccounts # 社交账号
games   # 游戏
books   #书籍
```
`baseInfo`主要包含年龄，性别，坐标，状态，格式如下，**注意空格缩进哦**
``` yaml
baseInfo:
  on: true # 是否显示
  age: 99 # 年龄
  sex: '男' # 性别
  coordinate: '火星' # 坐标
  status: '划水中' # 状态
```

`skills` 填写我的技能，格式如下，**注意空格缩进哦**
``` yaml
# 关于我 技能
skills:
  on: true # 是否显示
  data: # 这个data不能忘了，下面的字段注意缩进
    HTML5: # 这里写你的技能名称，如 HTML5或者java
      background: 'red' # 进度条颜色
      percent: 90% # 进度条百分比
    JavaScript:
      background: 'linear-gradient(120deg, #a1c4fd 0%, #c2e9fb 100%)'
      percent: 85%
    CSS:
      background: '#000'
      percent: 70%
```
`socialAccounts`填写我的社交账号，格式如下，**注意空格缩进哦**
``` yaml
socialAccounts: 
  on: true
  data: # 这个data不能忘了，下面的字段注意缩进
    QQ: # 社交软件名称
      icon: fa fa-qq  # 图标，可以为空，前面加上fa，假如图标名称叫fa-quora，就是 fa fa-quora, 
      name: 1730241541 # 账号名称
      url: 'http://www.baidu.com' # 账号链接地址
    微信:
      icon: fa fa-weixin
      name: 1730241541
      url: 'http://www.baidu.com'
```
> **注意**: icon使用的 [Font Awesome](https://fontawesome.dashgame.com/) 版本为 `4.7.0`。

`games` 填写我的游戏，格式如下，**注意空格缩进哦**
```yaml
games:
  on: true # 是否显示
  data: # 这个data不能忘了，下面的字段注意缩进
    王者荣耀: # 游戏名称，下面的img是游戏图片
      img: 'https://pic2.zhimg.com/80/v2-54730a36304842b86a57a237b8b39945_720w.jpg?source=1940ef5c'
    英雄杀:
      img: 'https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=1909008358,1888649581&fm=26&gp=0.jpg'
    和平精英:
      img: 'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1595596612190&di=dbf2030780758c4724ecb1f07f2f4f73&imgtype=0&src=http%3A%2F%2Fimgup04.51wxjz.com%2F51wxjz%2F2019-06%2F05%2F09%2F15596983468928_0.png'
    英雄联盟:
      img: 'https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=3035766587,2822701570&fm=26&gp=0.jpg'
```

`books` 填写我的书籍，格式如下，**注意空格缩进哦**
```yaml
books:
  on: true # 是否显示
  data: # 这个data不能忘了，下面的字段注意缩进
    明朝那些事儿: # 书籍名称，下面的img是书籍图片
      img: 'https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=2736238052,2078148140&fm=26&gp=0.jpg'
    春秋左传:
      img: 'https://pic2.zhimg.com/50/v2-6f33f60312de25ddcb795fc81ee91b38_720w.jpg?source=54b3c3a5'
    孙子兵法:
      img: 'https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=710999414,899378807&fm=26&gp=0.jpg'
```


### 新建友情连接 friends 页

`friends` 页是用来展示**友情连接**信息的页面，如果在你的博客 `source` 目录下还没有 `friends/index.md` 文件，那么你就需要新建一个，命令如下：

```bash
hexo new page "friends"
```

编辑你刚刚新建的页面文件 `/source/friends/index.md`，至少需要以下内容：

```yaml
---
title: friends
date: 2020-09-14 15:30:30
type: "friends"
layout: "friends"
---
```
同时，在你的博客 `source` 目录下新建 `_data` 目录，在 `_data` 目录中新建 `friends.json` 文件，文件内容如下所示：
```json
[{
  "avatar": "https://pic2.zhimg.com/80/v2-d1bd22e7dc847ae62028ae336d55ded9_720w.jpg?source=1940ef5c",
  "name": "如梦亦如幻",
  "introduction": "烟雨如江南",
  "url": "https://github.com/yuang01"
}, {
  "avatar": "https://pic1.zhimg.com/80/v2-1a60e33c33810a4d81a80282b8ca7a33_720w.jpg?source=1940ef5c",
  "name": "青灯暮雨",
  "introduction": "山水如墨染",
  "url": "https://github.com/yuang01"
}, {
  "avatar": "https://pic2.zhimg.com/80/v2-134122ca13d041f5ec1f2680f2677318_720w.jpg?source=1940ef5c",
  "name": "寄情山水花草间",
  "introduction": "宛如丹青未干",
  "url": "https://github.com/yuang01"
}]
```
### 中文链接转拼音（可选的）
如果你的文章名称是中文的，那么 Hexo 默认生成的永久链接也会有中文，这样不利于 `SEO`，且 `gitment` 评论对中文链接也不支持。我们可以用 [hexo-permalink-pinyin](https://github.com/viko16/hexo-permalink-pinyin) Hexo 插件使在生成文章时生成中文拼音的永久链接。
安装命令如下：

```bash
npm i hexo-permalink-pinyin --save
```

在 Hexo 根目录下的 `_config.yml` 文件中，新增以下的配置项：

```yaml
permalink_pinyin:
  enable: true
  separator: '-' # default: '-'
```
> **注**：除了此插件外，[hexo-abbrlink](https://github.com/rozbo/hexo-abbrlink) 插件也可以生成非中文的链接。

### 添加 RSS 订阅支持（可选的）

本主题中还使用到了 [hexo-generator-feed](https://github.com/hexojs/hexo-generator-feed) 的 Hexo 插件来做 `RSS`，安装命令如下：

```bash
npm install hexo-generator-feed --save
```

在 Hexo 根目录下的 `_config.yml` 文件中，新增以下的配置项：

```yaml
feed:
  type: atom
  path: atom.xml
  limit: 20
  hub:
  content:
  content_limit: 140
  content_limit_delim: ' '
  order_by: -date
```

### 首页轮播图
首页轮播图在`source/_posts/xxx.md`也就是文章页面配置，如果你想让某个文章放在首页轮播中，只用设置`swiper: true`即可，可以通过`swiperImg: xxx`来配置轮播图片，如下所示
```yaml
---
title: Hello world
date: 2019-01-20 21:11
swiper: true
swiperImg: 'https://ssyerv1.oss-cn-hangzhou.aliyuncs.com/picture/c080ff4434354e35af9dab0a3ee1b9f7.jpg!sswm'
---
我是文章内容
```
`swiperImg`可以是cdn地址，也可以是本地地址，例如`/medias/4.png`
可以通过主题文件夹下的`_config.yml`文件中的`swiper`属性对轮播进行调整

### 顶部导航
通过主题文件夹下的`_config.yml`文件中的`logo`属性设置网站logo，`Github`属性设置导航右侧的github，`menu`属性设置菜单，`headMenuFixed`属性设置导航是否随滚动条下拉固定

### 网站favicon
设置主题文件夹下的`_config.yml`文件中的`favicon`属性即可

### 回到顶部
设置主题文件夹下的`_config.yml`文件中的`goTop`属性即可控制隐藏显示

### 文章详情页图片放大功能 
设置主题文件夹下的`_config.yml`文件中的`fancybox`属性即可

### 修改页脚
页脚底部的网站统计功能，使用的是[不蒜子](http://busuanzi.ibruce.info/)，设置主题文件夹下的`_config.yml`文件中的`busuanzi`属性即可控制隐藏显示
页脚信息可以在`/layout/_partial/footer.ejs` 文件中进行手动修改。本主题使用[Font Awesome图标](http://www.fontawesome.com.cn/faicons/)
> **注意**: 本主题中使用的 `Font Awesome` 版本为 `4.7.0`。

### 修改打赏的二维码图片
设置主题文件夹下的`_config.yml`文件中的`donate`属性为true，然后更改`Alipay`和`WeChatpay`图片路径即可

### 文章详情页分享功能
设置主题文件夹下的`_config.yml`文件中的`sharejs`属性true或者false即可

### 点击出现爱心效果
设置主题文件夹下的`_config.yml`文件中的`clicklove`属性true或者false即可

### 复制成功提醒
当复制内容时候，是否显示复制成功提示 
设置主题文件夹下的`_config.yml`文件中的`copy`属性true或者false即可
```yaml
# 复制成功提示
copy:
  on: true
  title: '成功'
  content: '复制成功了哦'
```

### 雪花飘落和花瓣飘落特效
设置主题文件夹下的`_config.yml`文件中的`snow`或者`sakura`属性true或者false即可
```yaml
# 首页雪花飘落效果--冬天
snow:
  on: false
  onlyPc: false # 设为true，只有pc端显示雪花特效

# 首页花瓣飘落效果--春天
sakura:
  on: false
  onlyPc: false # 设为true，只有pc端显示花瓣特效
```

### 文章详情页的标题显示位置 
设置主题文件夹下的`_config.yml`文件中的`postTitleTop`属性true或者false即可，true的时候，显示在上方的图片中，false显示在文章内容上面

### 输入框打字特效
搜索弹框中的输入框打字特效，设置主题文件夹下的`_config.yml`文件中的`inputEffects`属性为true或者false即可。

### live-2d人物
设置主题文件夹下的`_config.yml`文件中的`live2d`属性为true或者false，可以通过`modelId`属性选择模型，注意，live-2d人物只有在屏幕宽度最小为992px的时候才显示
```yaml
modelId: 2  # 0 or 1 or 2 or 3 or 4 or 5 or 6
```

### 滚动动画
设置主题文件夹下的`_config.yml`文件中的`aos`属性对首页中的文章列表动画进行控制，具体参考官网[aos.js](https://github.com/michalsnik/aos#animations)

### 文章详情页目录 
设置主题文件夹下的`_config.yml`文件中的`toc`属性，控制其显示隐藏

### 音乐 
设置主题文件夹下的`_config.yml`文件中的`music`属性，控制其显示隐藏和其他一些调整, `music`中的`fixed`属性建议使用`true`
```yaml
music:
  on: true
  autoHide: true    # hide automaticaly
  server: netease   # 平台名称。netease：网易；tencent：腾讯；xiami：虾米；kugou：酷狗；baidu：百度
  type: playlist    # playlist：歌单；song：单曲；专辑：album；关键词：search；歌手：artist
  id: 442274724     # 音乐页面链接上的id号
  fixed: true       # 开启吸底模式，建议开启
  autoplay: false   # 是否自动播放
  theme: '#42b983'
  loop: 'all'       # 音频循环播放, 可选值: 'all', 'one', 'none'
  order: 'random'   # 音频循环顺序, 可选值: 'list', 'random'
  preload: 'auto'   # 预加载，可选值: 'none', 'metadata', 'auto'
  volume: 0.7       # 默认音量，请注意播放器会记忆用户设置，用户手动设置音量后默认音量即失效
  listFolded: true  # 列表默认折叠
  hideLrc: true     # 隐藏歌词
```

### 版权信息
可以在`source/_posts/xxx.md`文件中设置`copyright`true或者false，单独设置某个文章的版权信息是否显示，也可以在主题文件夹下的`_config.yml`文件中的`copyright`属性设置true或者false对所有文章的版权信息进行显示隐藏控制

### 文章置顶
可以在`source/_posts/xxx.md`文件中设置`top: true`，将该文章放在首页的文章置顶栏目中，可以在主题文件夹下的`_config.yml`文件中的`topArticle`属性设置true或者false控制首页的文章置顶栏目显示和隐藏。
```yaml
---
title: Hello World
date: 2019-05-21 21:11
top: true
---
我是文章内容
```

### 评论
主题中内置了`valine`, `miniValine`, `livere`, `gitment`, `gitalk`, `changyan`评论
通过主题文件夹下的`_config.yml`文件中的相应属性进行设置
推荐使用`valine`和`livere`
这里重点说一下`valine`评论配置
```yaml
valine:
  on: true # 是否启用
  appid: # 你的appid --> https://valine.js.org/quickstart.html，请阅读这个获取appid和appkey
  appkey: # 你的key
  avatar: '' # 匿名者头像选项 https://valine.js.org/avatar.html 访客的头像,最好启用下面的`requiredFields`中的邮箱必填，填写qq邮箱，头像会变成qq头像
  placeholder: '客官，说点什么吧' # 评论内容输入框的 placeholder
  master: 'xxxxxx' # 博主标签识别，博主邮箱md5 可以去md5加密网站，例如 https://md5jiami.51240.com/ ，将自己的邮箱输入， 得到 32位小写 的字符串填入这里
  friends: ['xxxxxxx', 'xxxxxx'] # 小伙伴的 邮箱md5， 是个数组
  requiredFields: ['nick', 'mail'] # 设置必填项 ['nick', 'mail'] nick为昵称必填， mail为邮箱必填, 空数组，则不校验
```
### 归档、标签、分类、关于我、友情链接页面图片自定义
通过主题文件夹下的`_config.yml`文件中的相应属性进行设置，属性如下：
``` yaml
# 归档页面图片 or 'http://xxx'
archiveImg: '/medias/archive.jpg'
# 标签页面图片
tagImg: '/medias/tag.jpg'
# 标签详情页面图片
tagDetailImg: '/medias/tagDetail.jpg'
# 分类页面图片
categoriesImg: '/medias/categories.jpg'
#分类详情页面图片
categoryDetailImg: '/medias/categoryDetail.jpg'
# 关于我页面图片
aboutImg: '/medias/about.jpg'
# 友情链接页面图片
friendsImg: '/medias/friend.jpg'
```

### 更改主题颜色
默认主题颜色是绿色(#42b983)，可以通过更改主题文件夹`hexo-theme-bamboo`下的文件：`source/css/_partial/custom.styl`,将文件中的所有(#42b983)颜色值替换成你想要的颜色，然后更改该文件下的`blockquote`背景颜色，代码如下:
```css
// 文章详情页的blockquote，md中的 > 标签的左边框和背景颜色
.post-detail {
  blockquote {
      border-left: 4px solid #42b983;
      background-color: rgba(66, 185, 131, .1); // 更改这个背景颜色为你想要的的颜色值
  }
}
```
blockquote样式指的是下面这个
> 我是blockquote

例如，我将该文件下的所有颜色设置为`skyblue`，显示效果如下
![theme-color](https://img13.360buyimg.com/ddimg/jfs/t1/120336/2/13322/273081/5f69b8d1E737e6277/8fdc796d2d3a82b3.png)

代码高亮颜色，可以通过之前介绍的代码高亮进行更改

## 文章 Front-matter 介绍
`Front-matter` 选项中的所有内容均为**非必填**的。但我仍然建议至少填写 `title` 和 `date` 的值。

| 配置选项   | 默认值                      | 描述                                                         |
| ---------- | --------------------------- | ------------------------------------------------------------ |
| title      | `Markdown` 的文件标题        | 文章标题，强烈建议填写此选项                                 |
| date       | 文件创建时的日期时间          | 发布时间，强烈建议填写此选项，且最好保证全局唯一  
| swiper     | false                       | 表示该文章是否需要加入到首页轮播封面中
| swiperImg  | 无                       | 表示该文章在首页轮播封面需要显示的图片路径，如果没有，则默认使用文章的特色图片
| top        | false                       | 表示该文章是否需要加入到首页的文章置顶栏目中
| comments   | false                       | 表示该文章是否需要评论
| img        | 无                          | 文章特征图，该文章显示的图片，没有则默认使用文章的特色图片
| categories | 无                          | 文章分类，本主题的分类表示宏观上大的分类，只建议一篇文章一个分类 |
| tags       | 无                          | 文章标签，一篇文章可以多个标签  

## 常见问题
代码高亮如遇到花括号变成了`&#123;&#125;`这样的字符串，在根目录下输入npm install hexo@4.2.1即可。

