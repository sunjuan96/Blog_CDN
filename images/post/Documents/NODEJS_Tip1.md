---
title: 显示文件夹的目录结构
date: 2018-7-30 15:58:17
tags: 经验
---


1. 安装nodejs下的mddir工具
`npm install mddir -g`
2. mddir全局环境设置
`ln -s /root/software/nodejs12.14/bin/mddir /usr/local/bin/`
3. 在待显示目录结果的文件夹下执行mddir命令
`mddir`
<!-- more -->
4. 将文件夹下生成的directoryList.md的内容复制到md文件中，用\```内容\```包含
```
|-- Documents
    |-- .gitignore
    |-- _config.yml
    |-- db.json
    |-- package-lock.json
    |-- package.json
    |-- .deploy_git
    |   |-- content.json
    |   |-- index.html
    |   |-- main.0cf68a.css
    |   |-- main.0cf68a.js
    |   |-- mobile.992cbe.js
    |   |-- slider.e37972.js
    |   |-- 2018
    |   |   |-- 07
    |   |       |-- 28
    |   |           |-- BlogGenerate
    |   |               |-- github_1.png
    |   |               |-- github_2.png
    |   |               |-- github_3.png
    |   |               |-- image_1.png
    |   |               |-- index.html
    |   |               |-- nodejs_1.png
    |   |               |-- theme_1.png
    |   |-- 2019
    |   |   |-- 12
    |   |       |-- 27
    |   |           |-- hello-world
    |   |               |-- index.html
    |   |-- archives
    |   |   |-- index.html
    |   |   |-- 2018
    |   |   |   |-- index.html
    |   |   |   |-- 07
    |   |   |       |-- index.html
    |   |   |-- 2019
    |   |       |-- index.html
    |   |       |-- 12
    |   |           |-- index.html
    |   |-- fonts
    |   |   |-- default-skin.b257fa.svg
    |   |   |-- iconfont.16acc2.ttf
    |   |   |-- iconfont.45d7ee.svg
    |   |   |-- iconfont.8c627f.woff
    |   |   |-- iconfont.b322fa.eot
    |   |   |-- tooltip.4004ff.svg
    |   |-- img
    |   |   |-- default-skin.png
    |   |   |-- preloader.gif
    |   |   |-- scrollbar_arrow.png
    |   |-- tags
    |       |-- 技能
    |           |-- index.html
    |-- public
    |   |-- content.json
    |   |-- index.html
    |   |-- main.0cf68a.css
    |   |-- main.0cf68a.js
    |   |-- mobile.992cbe.js
    |   |-- slider.e37972.js
    |   |-- 2018
    |   |   |-- 07
    |   |       |-- 28
    |   |           |-- BlogGenerate
    |   |               |-- github_1.png
    |   |               |-- github_2.png
    |   |               |-- github_3.png
    |   |               |-- image_1.png
    |   |               |-- index.html
    |   |               |-- nodejs_1.png
    |   |               |-- theme_1.png
    |   |               |-- theme_2.png
    |   |-- 2019
    |   |   |-- 12
    |   |       |-- 27
    |   |       |   |-- hello-world
    |   |       |       |-- index.html
    |   |       |-- 29
    |   |           |-- BlogChange
    |   |               |-- index.html
    |   |-- archives
    |   |   |-- index.html
    |   |   |-- 2018
    |   |   |   |-- index.html
    |   |   |   |-- 07
    |   |   |       |-- index.html
    |   |   |-- 2019
    |   |       |-- index.html
    |   |       |-- 12
    |   |           |-- index.html
    |   |-- fonts
    |   |   |-- default-skin.b257fa.svg
    |   |   |-- iconfont.16acc2.ttf
    |   |   |-- iconfont.45d7ee.svg
    |   |   |-- iconfont.8c627f.woff
    |   |   |-- iconfont.b322fa.eot
    |   |   |-- tooltip.4004ff.svg
    |   |-- img
    |   |   |-- default-skin.png
    |   |   |-- preloader.gif
    |   |   |-- scrollbar_arrow.png
    |   |-- tags
    |       |-- 技能
    |           |-- index.html
    |-- scaffolds
    |   |-- draft.md
    |   |-- page.md
    |   |-- post.md
    |-- source
    |   |-- _posts
    |       |-- BlogChange.md
    |       |-- BlogGenerate.md
    |       |-- hello-world.md
    |       |-- BlogChange
    |       |-- BlogGenerate
    |           |-- github_1.png
    |           |-- github_2.png
    |           |-- github_3.png
    |           |-- image_1.png
    |           |-- nodejs_1.png
    |           |-- theme_1.png
    |           |-- theme_2.png
    |-- themes
        |-- landscape
        |   |-- .gitignore
        |   |-- Gruntfile.js
        |   |-- LICENSE
        |   |-- README.md
        |   |-- _config.yml
        |   |-- package.json
        |   |-- languages
        |   |   |-- de.yml
        |   |   |-- default.yml
        |   |   |-- es.yml
        |   |   |-- fr.yml
        |   |   |-- ja.yml
        |   |   |-- ko.yml
        |   |   |-- nl.yml
        |   |   |-- no.yml
        |   |   |-- pt.yml
        |   |   |-- ru.yml
        |   |   |-- zh-CN.yml
        |   |   |-- zh-TW.yml
        |   |-- layout
        |   |   |-- archive.ejs
        |   |   |-- category.ejs
        |   |   |-- index.ejs
        |   |   |-- layout.ejs
        |   |   |-- page.ejs
        |   |   |-- post.ejs
        |   |   |-- tag.ejs
        |   |   |-- _partial
        |   |   |   |-- after-footer.ejs
        |   |   |   |-- archive-post.ejs
        |   |   |   |-- archive.ejs
        |   |   |   |-- article.ejs
        |   |   |   |-- footer.ejs
        |   |   |   |-- gauges-analytics.ejs
        |   |   |   |-- google-analytics.ejs
        |   |   |   |-- head.ejs
        |   |   |   |-- header.ejs
        |   |   |   |-- mobile-nav.ejs
        |   |   |   |-- sidebar.ejs
        |   |   |   |-- post
        |   |   |       |-- category.ejs
        |   |   |       |-- date.ejs
        |   |   |       |-- gallery.ejs
        |   |   |       |-- nav.ejs
        |   |   |       |-- tag.ejs
        |   |   |       |-- title.ejs
        |   |   |-- _widget
        |   |       |-- archive.ejs
        |   |       |-- category.ejs
        |   |       |-- recent_posts.ejs
        |   |       |-- tag.ejs
        |   |       |-- tagcloud.ejs
        |   |-- scripts
        |   |   |-- fancybox.js
        |   |-- source
        |       |-- css
        |       |   |-- _extend.styl
        |       |   |-- _variables.styl
        |       |   |-- style.styl
        |       |   |-- _partial
        |       |   |   |-- archive.styl
        |       |   |   |-- article.styl
        |       |   |   |-- comment.styl
        |       |   |   |-- footer.styl
        |       |   |   |-- header.styl
        |       |   |   |-- highlight.styl
        |       |   |   |-- mobile.styl
        |       |   |   |-- sidebar-aside.styl
        |       |   |   |-- sidebar-bottom.styl
        |       |   |   |-- sidebar.styl
        |       |   |-- _util
        |       |   |   |-- grid.styl
        |       |   |   |-- mixin.styl
        |       |   |-- fonts
        |       |   |   |-- FontAwesome.otf
        |       |   |   |-- fontawesome-webfont.eot
        |       |   |   |-- fontawesome-webfont.svg
        |       |   |   |-- fontawesome-webfont.ttf
        |       |   |   |-- fontawesome-webfont.woff
        |       |   |-- images
        |       |       |-- banner.jpg
        |       |-- fancybox
        |       |   |-- blank.gif
        |       |   |-- fancybox_loading.gif
        |       |   |-- fancybox_loading@2x.gif
        |       |   |-- fancybox_overlay.png
        |       |   |-- fancybox_sprite.png
        |       |   |-- fancybox_sprite@2x.png
        |       |   |-- jquery.fancybox.css
        |       |   |-- jquery.fancybox.js
        |       |   |-- jquery.fancybox.pack.js
        |       |   |-- helpers
        |       |       |-- fancybox_buttons.png
        |       |       |-- jquery.fancybox-buttons.css
        |       |       |-- jquery.fancybox-buttons.js
        |       |       |-- jquery.fancybox-media.js
        |       |       |-- jquery.fancybox-thumbs.css
        |       |       |-- jquery.fancybox-thumbs.js
        |       |-- js
        |           |-- script.js
        |-- next
        |   |-- .editorconfig
        |   |-- .eslintrc.json
        |   |-- .gitattributes
        |   |-- .gitignore
        |   |-- .stylintrc
        |   |-- .travis.yml
        |   |-- LICENSE.md
        |   |-- README.md
        |   |-- _config.yml
        |   |-- crowdin.yml
        |   |-- gulpfile.js
        |   |-- package.json
        |   |-- .github
        |   |   |-- CODE_OF_CONDUCT.md
        |   |   |-- CONTRIBUTING.md
        |   |   |-- PULL_REQUEST_TEMPLATE.md
        |   |   |-- config.yml
        |   |   |-- issue_label_bot.yaml
        |   |   |-- lock.yml
        |   |   |-- mergeable.yml
        |   |   |-- release-drafter.yml
        |   |   |-- stale.yml
        |   |   |-- support.yml
        |   |   |-- ISSUE_TEMPLATE
        |   |       |-- bug-report.md
        |   |       |-- feature-request.md
        |   |       |-- other.md
        |   |       |-- question.md
        |   |-- docs
        |   |   |-- AGPL3.md
        |   |   |-- ALGOLIA-SEARCH.md
        |   |   |-- AUTHORS.md
        |   |   |-- DATA-FILES.md
        |   |   |-- INSTALLATION.md
        |   |   |-- LEANCLOUD-COUNTER-SECURITY.md
        |   |   |-- LICENSE.txt
        |   |   |-- MATH.md
        |   |   |-- UPDATE-FROM-5.1.X.md
        |   |   |-- ru
        |   |   |   |-- DATA-FILES.md
        |   |   |   |-- INSTALLATION.md
        |   |   |   |-- README.md
        |   |   |   |-- UPDATE-FROM-5.1.X.md
        |   |   |-- zh-CN
        |   |       |-- ALGOLIA-SEARCH.md
        |   |       |-- CODE_OF_CONDUCT.md
        |   |       |-- CONTRIBUTING.md
        |   |       |-- DATA-FILES.md
        |   |       |-- INSTALLATION.md
        |   |       |-- LEANCLOUD-COUNTER-SECURITY.md
        |   |       |-- MATH.md
        |   |       |-- README.md
        |   |       |-- UPDATE-FROM-5.1.X.md
        |   |-- languages
        |   |   |-- de.yml
        |   |   |-- default.yml
        |   |   |-- en.yml
        |   |   |-- es.yml
        |   |   |-- fa.yml
        |   |   |-- fr.yml
        |   |   |-- hu.yml
        |   |   |-- id.yml
        |   |   |-- it.yml
        |   |   |-- ja.yml
        |   |   |-- ko.yml
        |   |   |-- nl.yml
        |   |   |-- pt-BR.yml
        |   |   |-- pt.yml
        |   |   |-- ru.yml
        |   |   |-- tr.yml
        |   |   |-- uk.yml
        |   |   |-- vi.yml
        |   |   |-- zh-CN.yml
        |   |   |-- zh-HK.yml
        |   |   |-- zh-TW.yml
        |   |-- layout
        |   |   |-- _layout.swig
        |   |   |-- archive.swig
        |   |   |-- category.swig
        |   |   |-- index.swig
        |   |   |-- page.swig
        |   |   |-- post.swig
        |   |   |-- tag.swig
        |   |   |-- _macro
        |   |   |   |-- post-collapse.swig
        |   |   |   |-- post.swig
        |   |   |   |-- sidebar.swig
        |   |   |-- _partials
        |   |   |   |-- comments.swig
        |   |   |   |-- footer.swig
        |   |   |   |-- pagination.swig
        |   |   |   |-- widgets.swig
        |   |   |   |-- head
        |   |   |   |   |-- head-unique.swig
        |   |   |   |   |-- head.swig
        |   |   |   |-- header
        |   |   |   |   |-- brand.swig
        |   |   |   |   |-- index.swig
        |   |   |   |   |-- menu-item.swig
        |   |   |   |   |-- menu.swig
        |   |   |   |   |-- sub-menu.swig
        |   |   |   |-- page
        |   |   |   |   |-- breadcrumb.swig
        |   |   |   |   |-- page-header.swig
        |   |   |   |-- post
        |   |   |   |   |-- post-copyright.swig
        |   |   |   |   |-- post-footer.swig
        |   |   |   |   |-- post-related.swig
        |   |   |   |   |-- post-reward.swig
        |   |   |   |-- search
        |   |   |   |   |-- algolia-search.swig
        |   |   |   |   |-- index.swig
        |   |   |   |   |-- localsearch.swig
        |   |   |   |-- sidebar
        |   |   |       |-- site-overview.swig
        |   |   |-- _scripts
        |   |   |   |-- index.swig
        |   |   |   |-- noscript.swig
        |   |   |   |-- pjax.swig
        |   |   |   |-- three.swig
        |   |   |   |-- vendors.swig
        |   |   |   |-- pages
        |   |   |   |   |-- schedule.swig
        |   |   |   |-- schemes
        |   |   |       |-- gemini.swig
        |   |   |       |-- mist.swig
        |   |   |       |-- muse.swig
        |   |   |       |-- pisces.swig
        |   |   |-- _third-party
        |   |       |-- baidu-push.swig
        |   |       |-- index.swig
        |   |       |-- quicklink.swig
        |   |       |-- rating.swig
        |   |       |-- analytics
        |   |       |   |-- baidu-analytics.swig
        |   |       |   |-- google-analytics.swig
        |   |       |   |-- growingio.swig
        |   |       |   |-- index.swig
        |   |       |-- chat
        |   |       |   |-- chatra.swig
        |   |       |   |-- tidio.swig
        |   |       |-- comments
        |   |       |   |-- changyan.swig
        |   |       |   |-- disqus.swig
        |   |       |   |-- disqusjs.swig
        |   |       |   |-- gitalk.swig
        |   |       |   |-- livere.swig
        |   |       |   |-- valine.swig
        |   |       |-- math
        |   |       |   |-- index.swig
        |   |       |   |-- katex.swig
        |   |       |   |-- mathjax.swig
        |   |       |-- search
        |   |       |   |-- algolia-search.swig
        |   |       |   |-- localsearch.swig
        |   |       |   |-- swiftype.swig
        |   |       |-- statistics
        |   |       |   |-- busuanzi-counter.swig
        |   |       |   |-- cnzz-analytics.swig
        |   |       |   |-- firestore.swig
        |   |       |   |-- index.swig
        |   |       |   |-- lean-analytics.swig
        |   |       |-- tags
        |   |           |-- mermaid.swig
        |   |           |-- pdf.swig
        |   |-- scripts
        |   |   |-- renderer.js
        |   |   |-- events
        |   |   |   |-- index.js
        |   |   |   |-- lib
        |   |   |       |-- config.js
        |   |   |       |-- injects-point.js
        |   |   |       |-- injects.js
        |   |   |-- filters
        |   |   |   |-- default-injects.js
        |   |   |   |-- front-matter.js
        |   |   |   |-- locals.js
        |   |   |   |-- minify.js
        |   |   |   |-- post.js
        |   |   |   |-- comment
        |   |   |       |-- changyan.js
        |   |   |       |-- common.js
        |   |   |       |-- default-config.js
        |   |   |       |-- disqus.js
        |   |   |       |-- disqusjs.js
        |   |   |       |-- gitalk.js
        |   |   |       |-- livere.js
        |   |   |       |-- valine.js
        |   |   |-- helpers
        |   |   |   |-- engine.js
        |   |   |   |-- font.js
        |   |   |   |-- next-url.js
        |   |   |-- tags
        |   |       |-- button.js
        |   |       |-- caniuse.js
        |   |       |-- center-quote.js
        |   |       |-- group-pictures.js
        |   |       |-- label.js
        |   |       |-- mermaid.js
        |   |       |-- note.js
        |   |       |-- pdf.js
        |   |       |-- tabs.js
        |   |       |-- video.js
        |   |-- source
        |       |-- css
        |       |   |-- main.styl
        |       |   |-- _common
        |       |   |   |-- components
        |       |   |   |   |-- back-to-top-sidebar.styl
        |       |   |   |   |-- back-to-top.styl
        |       |   |   |   |-- components.styl
        |       |   |   |   |-- rainbow.styl
        |       |   |   |   |-- reading-progress.styl
        |       |   |   |   |-- pages
        |       |   |   |   |   |-- breadcrumb.styl
        |       |   |   |   |   |-- categories.styl
        |       |   |   |   |   |-- pages.styl
        |       |   |   |   |   |-- schedule.styl
        |       |   |   |   |   |-- tag-cloud.styl
        |       |   |   |   |-- post
        |       |   |   |   |   |-- post-collapse.styl
        |       |   |   |   |   |-- post-copyright.styl
        |       |   |   |   |   |-- post-eof.styl
        |       |   |   |   |   |-- post-expand.styl
        |       |   |   |   |   |-- post-gallery.styl
        |       |   |   |   |   |-- post-header.styl
        |       |   |   |   |   |-- post-nav.styl
        |       |   |   |   |   |-- post-reward.styl
        |       |   |   |   |   |-- post-rtl.styl
        |       |   |   |   |   |-- post-tags.styl
        |       |   |   |   |   |-- post-widgets.styl
        |       |   |   |   |   |-- post.styl
        |       |   |   |   |-- third-party
        |       |   |   |       |-- gitalk.styl
        |       |   |   |       |-- math.styl
        |       |   |   |       |-- related-posts.styl
        |       |   |   |       |-- search.styl
        |       |   |   |       |-- third-party.styl
        |       |   |   |-- outline
        |       |   |   |   |-- mobile.styl
        |       |   |   |   |-- outline.styl
        |       |   |   |   |-- footer
        |       |   |   |   |   |-- footer.styl
        |       |   |   |   |-- header
        |       |   |   |   |   |-- bookmark.styl
        |       |   |   |   |   |-- github-banner.styl
        |       |   |   |   |   |-- header.styl
        |       |   |   |   |   |-- headerband.styl
        |       |   |   |   |   |-- menu.styl
        |       |   |   |   |   |-- site-meta.styl
        |       |   |   |   |   |-- site-nav.styl
        |       |   |   |   |-- sidebar
        |       |   |   |       |-- sidebar-author-links.styl
        |       |   |   |       |-- sidebar-author.styl
        |       |   |   |       |-- sidebar-blogroll.styl
        |       |   |   |       |-- sidebar-button.styl
        |       |   |   |       |-- sidebar-dimmer.styl
        |       |   |   |       |-- sidebar-nav.styl
        |       |   |   |       |-- sidebar-toc.styl
        |       |   |   |       |-- sidebar-toggle.styl
        |       |   |   |       |-- sidebar.styl
        |       |   |   |       |-- site-state.styl
        |       |   |   |-- scaffolding
        |       |   |       |-- base.styl
        |       |   |       |-- buttons.styl
        |       |   |       |-- comments.styl
        |       |   |       |-- normalize.styl
        |       |   |       |-- pagination.styl
        |       |   |       |-- scaffolding.styl
        |       |   |       |-- tables.styl
        |       |   |       |-- toggles.styl
        |       |   |       |-- highlight
        |       |   |       |   |-- copy-code.styl
        |       |   |       |   |-- diff.styl
        |       |   |       |   |-- highlight.styl
        |       |   |       |   |-- theme.styl
        |       |   |       |-- tags
        |       |   |           |-- blockquote-center.styl
        |       |   |           |-- group-pictures.styl
        |       |   |           |-- label.styl
        |       |   |           |-- note.styl
        |       |   |           |-- pdf.styl
        |       |   |           |-- tabs.styl
        |       |   |           |-- tags.styl
        |       |   |-- _mixins
        |       |   |   |-- Gemini.styl
        |       |   |   |-- Mist.styl
        |       |   |   |-- Muse.styl
        |       |   |   |-- Pisces.styl
        |       |   |   |-- base.styl
        |       |   |-- _schemes
        |       |   |   |-- Gemini
        |       |   |   |   |-- index.styl
        |       |   |   |-- Mist
        |       |   |   |   |-- _header.styl
        |       |   |   |   |-- _layout.styl
        |       |   |   |   |-- _menu.styl
        |       |   |   |   |-- _posts-expand.styl
        |       |   |   |   |-- index.styl
        |       |   |   |-- Muse
        |       |   |   |   |-- _header.styl
        |       |   |   |   |-- _layout.styl
        |       |   |   |   |-- _menu.styl
        |       |   |   |   |-- _sidebar.styl
        |       |   |   |   |-- _sub-menu.styl
        |       |   |   |   |-- index.styl
        |       |   |   |-- Pisces
        |       |   |       |-- _header.styl
        |       |   |       |-- _layout.styl
        |       |   |       |-- _menu.styl
        |       |   |       |-- _sidebar.styl
        |       |   |       |-- _sub-menu.styl
        |       |   |       |-- index.styl
        |       |   |-- _variables
        |       |       |-- Gemini.styl
        |       |       |-- Mist.styl
        |       |       |-- Muse.styl
        |       |       |-- Pisces.styl
        |       |       |-- base.styl
        |       |-- images
        |       |   |-- algolia_logo.svg
        |       |   |-- apple-touch-icon-next.png
        |       |   |-- avatar.gif
        |       |   |-- cc-by-nc-nd.svg
        |       |   |-- cc-by-nc-sa.svg
        |       |   |-- cc-by-nc.svg
        |       |   |-- cc-by-nd.svg
        |       |   |-- cc-by-sa.svg
        |       |   |-- cc-by.svg
        |       |   |-- cc-zero.svg
        |       |   |-- favicon-16x16-next.png
        |       |   |-- favicon-32x32-next.png
        |       |   |-- logo.svg
        |       |   |-- quote-l.svg
        |       |   |-- quote-r.svg
        |       |-- js
        |       |   |-- algolia-search.js
        |       |   |-- bookmark.js
        |       |   |-- local-search.js
        |       |   |-- motion.js
        |       |   |-- next-boot.js
        |       |   |-- utils.js
        |       |   |-- schemes
        |       |       |-- muse.js
        |       |       |-- pisces.js
        |       |-- lib
        |           |-- anime.min.js
        |           |-- font-awesome
        |           |   |-- .bower.json
        |           |   |-- .gitignore
        |           |   |-- .npmignore
        |           |   |-- HELP-US-OUT.txt
        |           |   |-- bower.json
        |           |   |-- css
        |           |   |   |-- font-awesome.css
        |           |   |   |-- font-awesome.css.map
        |           |   |   |-- font-awesome.min.css
        |           |   |-- fonts
        |           |       |-- fontawesome-webfont.eot
        |           |       |-- fontawesome-webfont.woff
        |           |       |-- fontawesome-webfont.woff2
        |           |-- velocity
        |               |-- velocity.min.js
        |               |-- velocity.ui.min.js
        |-- yilia
            |-- .babelrc
            |-- .editorconfig
            |-- .eslintignore
            |-- .eslintrc.js
            |-- .gitattributes
            |-- .gitignore
            |-- README.md
            |-- _config.yml
            |-- package.json
            |-- webpack.config.js
            |-- languages
            |   |-- default.yml
            |   |-- fr.yml
            |   |-- nl.yml
            |   |-- no.yml
            |   |-- ru.yml
            |   |-- zh-CN.yml
            |   |-- zh-tw.yml
            |-- layout
            |   |-- archive.ejs
            |   |-- category.ejs
            |   |-- index.ejs
            |   |-- layout.ejs
            |   |-- page.ejs
            |   |-- post.ejs
            |   |-- tag.ejs
            |   |-- _partial
            |       |-- after-footer.ejs
            |       |-- archive-post.ejs
            |       |-- archive.ejs
            |       |-- article.ejs
            |       |-- aside.ejs
            |       |-- baidu-analytics.ejs
            |       |-- css.ejs
            |       |-- footer.ejs
            |       |-- google-analytics.ejs
            |       |-- head.ejs
            |       |-- header.ejs
            |       |-- left-col.ejs
            |       |-- mathjax.ejs
            |       |-- mobile-nav.ejs
            |       |-- script.ejs
            |       |-- toc.ejs
            |       |-- tools.ejs
            |       |-- viewer.ejs
            |       |-- post
            |           |-- category.ejs
            |           |-- changyan.ejs
            |           |-- date.ejs
            |           |-- duoshuo.ejs
            |           |-- gitment.ejs
            |           |-- nav.ejs
            |           |-- share.ejs
            |           |-- tag.ejs
            |           |-- title.ejs
            |           |-- wangyiyun.ejs
            |-- source
            |   |-- main.0cf68a.css
            |   |-- main.0cf68a.js
            |   |-- mobile.992cbe.js
            |   |-- slider.e37972.js
            |   |-- fonts
            |   |   |-- default-skin.b257fa.svg
            |   |   |-- iconfont.16acc2.ttf
            |   |   |-- iconfont.45d7ee.svg
            |   |   |-- iconfont.8c627f.woff
            |   |   |-- iconfont.b322fa.eot
            |   |   |-- tooltip.4004ff.svg
            |   |-- img
            |       |-- default-skin.png
            |       |-- preloader.gif
            |       |-- scrollbar_arrow.png
            |-- source-src
                |-- css.ejs
                |-- script.ejs
                |-- css
                |   |-- _core.scss
                |   |-- _function.scss
                |   |-- archive.scss
                |   |-- article-inner.scss
                |   |-- article-main.scss
                |   |-- article-nav.scss
                |   |-- article.scss
                |   |-- aside.scss
                |   |-- comment.scss
                |   |-- fonts.scss
                |   |-- footer.scss
                |   |-- global.scss
                |   |-- grid.scss
                |   |-- highlight.scss
                |   |-- left.scss
                |   |-- main.scss
                |   |-- mobile-slider.scss
                |   |-- mobile.scss
                |   |-- page.scss
                |   |-- reward.scss
                |   |-- scroll.scss
                |   |-- share.scss
                |   |-- social.scss
                |   |-- tags-cloud.scss
                |   |-- tags.scss
                |   |-- tools.scss
                |   |-- tooltip.scss
                |   |-- core
                |   |   |-- _animation.scss
                |   |   |-- _media-queries.scss
                |   |   |-- _mixin.scss
                |   |   |-- _reset.scss
                |   |   |-- _variables.scss
                |   |-- fonts
                |   |   |-- iconfont.eot
                |   |   |-- iconfont.svg
                |   |   |-- iconfont.ttf
                |   |   |-- iconfont.woff
                |   |-- img
                |       |-- checkered-pattern.png
                |       |-- scrollbar_arrow.png
                |       |-- tooltip.svg
                |-- js
                    |-- Q.js
                    |-- anm.js
                    |-- aside.js
                    |-- browser.js
                    |-- fix.js
                    |-- main.js
                    |-- mobile.js
                    |-- report.js
                    |-- share.js
                    |-- slider.js
                    |-- util.js
                    |-- viewer.js
```






