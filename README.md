# hexo-butterfly-categories-card-fork

虽然可以通过 hexo d 正常部署，但由于我使用了 GitHub Actions 进行自动化部署，流程中的 npm install 会重新拉取依赖，从而覆盖我本地对插件源代码的修改。鉴于原插件作者已长期未更新，我选择复制原版代码并进行适度微调，以便自用和后续维护。

* 本包为 hexo-butterfly-categories-card 的复制版本，基于原作者的结构进行调整
* 移除了分类卡片底部文字的滑动显示效果
* 修复了网页中分类目录重复的问题
* 参考链接：
    * [akilar - 首页分类卡片](https://akilar.top/posts/a9131002/)
    * [kukual - butterfly主题魔改10：分类页面魔改](https://kukual.github.io/posts/a7bebfb0/index.html)
    * [ll.sc.cn -【butterfly】分类磁贴插件版](https://ll.sc.cn/posts/ab72/)

个人的butterfly主题魔改也参考了大量[akilar](https://github.com/Akilarlxh) 的文章，再次感谢该插件原作者[akilar](https://github.com/Akilarlxh) 

---

给`hexo-theme-butterfly`添加 [首页分类卡片](https://akilar.top/posts/a9131002/)

# 安装

1. 安装插件,在博客根目录`[Blogroot]`下打开终端，运行以下指令：
  ```bash
  npm install hexo-butterfly-categories-card --save
  ```

2. 添加配置信息，以下为写法示例
  在站点配置文件`_config.yml`或者主题配置文件`_config.butterfly.yml`中添加

  ```yaml
  # hexo-butterfly-categories-card
  # see https://akilar.top/posts/a9131002/
  categoryBar:
    enable: true # 开关
    priority: 5 #过滤器优先权
    enable_page: / # 应用页面
    layout: # 挂载容器类型
      type: id
      name: recent-posts
      index: 0
    column: odd # odd：3列 | even：4列
    row: 1 #显示行数，默认两行，超过行数切换为滚动显示
    message:
      - descr: Ubuntu指南
        cover: https://npm.elemecdn.com/akilar-candyassets/image/cover1.webp
      - descr: 玩转Win10
        cover: https://npm.elemecdn.com/akilar-candyassets/image/cover2.webp
      - descr: 长篇小说连载
        cover: https://npm.elemecdn.com/akilar-candyassets/image/cover3.webp
      - descr: 个人日记
        cover: https://npm.elemecdn.com/akilar-candyassets/image/cover4.webp
      - descr: 诗词歌赋
        cover: https://npm.elemecdn.com/akilar-candyassets/image/cover5.webp
      - descr: 杂谈教程
        cover: https://npm.elemecdn.com/akilar-candyassets/image/cover6.webp
    custom_css: https://npm.elemecdn.com/hexo-butterfly-categories-card/lib/categorybar.css
  ```
3. 参数释义

  |参数|备选值/类型|释义|
  |:--|:--|:--|
  |priority|number|【可选】过滤器优先级，数值越小，执行越早，默认为10，选填|
  |enable|true/false|【必选】控制开关|
  |enable_page|path/all|【可选】填写想要应用的页面的相对路径（即路由地址）,如根目录就填'/',分类页面就填'/categories/'。若要应用于所有页面，就填'all'，默认为'/'|
  |layout.type|id/class|【可选】挂载容器类型，填写id或class，不填则默认为id|
  |layout.name|text|【必选】挂载容器名称|
  |layout.index|0和正整数|【可选】前提是layout.type为class，因为同一页面可能有多个class，此项用来确认究竟排在第几个顺位|
  |column|odd/even|【可选】显示列数，考虑到比例问题，只提供3列和4列，odd为3列， even为4列|
  |row|number|【可选】显示行数，默认两行，超过行数切换为滚动显示|
  |message.descr|text|分类描述,需要和你自己的文章分类一一对应。|
  |message.cover|url|分类背景,需要和你自己的文章分类一一对应。|
  |custom_css|url|【可选】自定义样式，会替换默认的css链接，可以下载文档给出的cdn链接后自主修改|

# 截图
![](https://npm.elemecdn.com/akilar-candyassets/image/af2f14fe.png)

# 更新记录
- 2022-03-04：1.0.0
  1. 弃用3.0方案，冰老师的原始布局与figure标签样式严重耦合。
  2. 沿用4.0方案，将自适应样式与配置关联。
  3. 列数样式整合进html.pug，用户无法再通过配置项以外的方式调整行数。
  4. 调用pjax.loadURL()方法实现不间断跳转，兼容aplayer全局音乐。
  5. 卡片链接、名称通过index.js直接生成，需要用户自行根据生成后的卡片添加描述和封面。
- 2022-03-03：0.0.11
  1. 初步修复样式bug，等待调整自适应样式
- 2021-08-25：0.0.10
  1. 沿用源码修改方案3.0版本，初步实现界面挂载
