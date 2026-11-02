CLAUDE OPUS 5.5 · MOTION ARCHIVE
=================================

这是多页面静态网站，不是单页面切换。

【网页结构】
index.html                         首页 / 全部作品目录
assets/css/style.css               全站统一样式（Claude 橙色视觉）
assets/js/works.js                 作品资料、首页卡片和提示词展示内容
works/                              每个作品一个独立文件夹
  01_echoes_in_mist/
    index.html                     这一个作品自己的详情页
    video.mp4                      ← 放最终视频，固定文件名
    prompt.txt                     ← 放完整提示词
    project.zip                    ← 可选，供访客下载的工程压缩包
    project/                       ← 可选，工程源文件
    README_本作品文件放置说明.txt
  02_the_glasshouse/                同上
  03_after_the_glow/                同上
  04_blue_hour/                     同上

【最简单的加视频方法】
1. 打开 works 文件夹，选择对应作品文件夹。
2. 把 MP4 放进去，重命名为 video.mp4。
3. 刷新该作品详情页，即可播放。
4. 每个作品独立存放，不需要把视频混在一个总目录里。

【添加新作品】
1. 复制任意一个 works/作品文件夹，改成新的编号和名称。
2. 在新文件夹中替换 video.mp4、prompt.txt。
3. 打开 assets/js/works.js，在 WORKS 数组中复制一个对象，修改 id、标题、描述、分类、时长、prompt 等字段。
4. 复制一份详情页 HTML，并将 body 的 data-work 改成新的 id。
5. 首页会自动生成新作品卡片，链接指向 works/新作品文件夹/index.html。

【视频播放器与性能】
- 每个作品有独立详情页和独立 HTML5 播放器。
- 使用 preload="none"，页面不会预加载整部视频。
- 只有打开该作品页时才检查并载入当前 video.mp4。
- 浏览器原生 controls 支持播放、暂停、拖动进度、音量和全屏。
- 建议视频格式：MP4（H.264 视频 + AAC 音频）。
- 推荐使用 VS Code Live Server 或其他静态 HTTP 服务打开首页；部分浏览器对 file:// 下的 HEAD 检测有限制。

【工程下载】
每个作品详情页的工程下载按钮指向同目录 project.zip。
将工程源文件放入 project/ 后，压缩为 project.zip 即可。
