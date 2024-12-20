# 背景介绍
目前浏览器插件当中非常好用的沉浸式翻译在不开会员的情况下只能使用一些质量不是特别好的API，在插件官方的指引介绍文档当中给出了如何设置其他API的方式，不过像微软Azure和Google Cloud以及DeepL都有一定的额度限定。对于日常不是特别大量频繁使用而言其实能够满足需要了，但是今天看到了个这个项目：

[[项目地址](https://github.com/ifyour/deeplx-for-cloudflare)](https://github.com/ifyour/deeplx-for-cloudflare)

于是这个插件的使用效果体验又更加提升了一大截。
----
- 步骤简介

在Cloudflare设置页面中创建workers，在部署完成之后点击编辑代码，将github页面中的dist/index.js 代码覆盖原来的worker代码，再点击部署即可生效。

将需要进行翻译的操作的软件中设置deeplx的链接为生成的workers的地址即可。