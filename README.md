# hexo-butterfly-categorybar

给`hexo-theme-butterfly`添加 [首页分类卡片](https://akilar.top/posts/a9131002/)

# 安装

1. 安装插件,在博客根目录`[Blogroot]`下打开终端，运行以下指令：
  ```bash
  npm install hexo-butterfly-categorybar --save
  ```

2. 添加配置信息，以下为写法示例
  在站点配置文件`_config.yml`或者主题配置文件`_config.butterfly.yml`中添加

  ```yaml
  # hexo-butterfly-categorybar
  # see https://akilar.top/posts/a9131002/
  swiper:
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
      - name: ☕Akilarの马卡龙
        descr: 长篇小说连载
        cover: https://cdn.jsdelivr.net/npm/akilar-candyassets/image/cover1.webp
      - name: 🍡Akilarの糖葫芦
        descr: 杂谈教程
        cover: https://cdn.jsdelivr.net/npm/akilar-candyassets/image/cover2.webp
      - name: 🍨Akilarの棉花糖
        descr: 玩转Win10
        cover: https://cdn.jsdelivr.net/npm/akilar-candyassets/image/cover3.webp
      - name: 🍫Akilarの巧克力
        descr: Ubuntu指南
        cover: https://cdn.jsdelivr.net/npm/akilar-candyassets/image/cover4.webp
      - name: 🍬Akilarの泡泡糖
        descr: 个人日记
        cover: https://cdn.jsdelivr.net/npm/akilar-candyassets/image/cover5.webp
      - name: 🍰Akilarの太妃糖
        descr: 诗词歌赋
        cover: https://cdn.jsdelivr.net/npm/akilar-candyassets/image/cover6.webp
    custom:
      css: https://cdn.jsdelivr.net/npm/hexo-butterfly-categorybar/lib/categorybar.css
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
  |message.name|text|分类名称，需要和你自己的文章分类一一对应|
  |message.descr|text|分类描述|
  |message.cover|url|分类背景|
  |custom.css|url|【可选】自定义样式，会替换默认的css链接，可以下载文档给出的cdn链接后自主修改|

# 截图
![](https://cdn.jsdelivr.net/npm/akilar-candyassets/image/af2f14fe.png)
