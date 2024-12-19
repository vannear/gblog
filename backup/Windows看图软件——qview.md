今天清理Windows笔记本的时候发现，Windows自带的照片软件占用空间居然要800MB，而且那个功能总有残缺不全的地方，例如当浏览到一个文件夹中的最后一张图片的时候，Windows照片会一直卡在这个最后一张图片。

于是用谷歌搜索了一下，居然看到个reddit的帖子也在抱怨这件事情，而且有老哥给出了答案，主要是因为Windows的照片需要兼容X86 X64 arm平台，而且代码结构没有得到优化，虽然反应速度说不上慢，但这个占用的体积确实太抽象了。评论区老哥给出了一个开源免费的看图软件：qview。
[[软件官网](https://interversehq.com/qview/)](https://interversehq.com/qview/)

[[GitHub项目地址](https://github.com/jurplel/qView)](https://github.com/jurplel/qView) —— 如果觉得好用记得至少star一下

[[下载页](https://interversehq.com/qview/download/)](https://interversehq.com/qview/download/)

安装完之后，至少初步体验下来Windows照片的痛点都解决了，占用空间仅有80MB，并且支持windows macOS以及Linux。总体来说非常满意。