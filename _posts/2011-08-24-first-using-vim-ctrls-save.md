---
layout: post
title: 初用vim,让vim能CTRL+S保存
pid: 209
comments: true
tags: [VIM]
categories: [互联网络]
---
这两天一直在学习Linux中传说的编辑器之神VIM,初步使用感觉确实不错.虽然它的神处我还没有用到,但是界面给人的感觉很舒服.另外我使用了人网上淘来的字体,然后设置一个好的背景.打字看起来很惬意.呵呵.

昨天花了半天的时间,把VIM自带的帮助文档看的差不多了.但是VIM的快捷键确实太多,一次也记不住几个.所以还是要到以后用的时候再看才能派上用场.

但是,稍微配置一下还是要的.所以找了网上别人的配置文件.我自己又结合我的情况.也弄了一个自己的配置.
由于我用的是gnome-terminal终端,所以找了一个让VIM可以像windows中那样可以按CTRL+S就保存的方法.

不能使用此方法的原因是,在很多终端中，CTRL-S按键是有特殊用途的。
"CTRL-S：挂起终端（XON）
"CTRL-Q：恢复终端（XOFF）
"要禁止这些键盘映射，在~/.bashrc中加入

    stty -ixon

然后修改vim中的按键映射，在 ~/.vimrc中加入

    nmap <C-S> :update<CR>
    vmap <C-S> <C-C>:update<CR>
    imap <C-S> <C-O>:update<CR>

这样就可以在普通模式,插入模式,还有可视模式中使用CTRL+S保存文件了.

另外 使用vim的好处,我发现就是可以按照自己的习惯对所有的按键进行重新映射.可以更加符合自己的喜好,这可能就是为什么这么多人喜欢使用它的原因吧.别处的一个原因就是编程的时候的插件选择.呵呵 这个我以后才能体会到.