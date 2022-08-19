# Vim

> VimTutor: https://blog.csdn.net/weixin_50792396/article/details/118762237

## NeoVim

## SpaceVim

> https://spacevim.org/

### 字体导致的报错

`Unknown font: SauceCodePro Nerd Font Mono`

解决方案一:
更改字体配置 & 字体图标相关的配置

```sh
# install nerd fonts
guifont = "Cascadia Code"
# statusline_separator = "arrow"
# statusline_separator = "arrow"
statusline_iseparator = "nil"
statusline_iseparator = "bar"
enable_tabline_filetype_icon = false
```

解决方案二:
下载安装对应的 Nerd 字体 => 建议只下载匹配的字体

[Nerd 字体下载](https://www.nerdfonts.com/font-downloads)

[SauceCodePro Nerd Font v2.1.0](https://github.com/ryanoasis/nerd-fonts/releases/download/v2.1.0/SourceCodePro.zip)

可以安装这个压缩包里的全部文件,也可以安装里面的全部 mono 字体(挑选有点麻烦)

### 插件安装问题

> 问题描述:
> 由于网络原因,插件的安装很慢,经常会出现安装失败或...
> 在 install/building 插件的时候就关闭了 NeoVim
> 再次打开自动安装的清单就可能会少一些插件(未安装好,可能建立好了对应的文件导致插件管理器判断错误)
> 导致后续使用过程中的报错,影响运行

更新插件: `SPUpdate` 这一命令将会更新所有插件，包括 SpaceVim 自身(这一命令也支持参数，参数为插件名称，可同时添加多个插件名称作为参数， 同时可以使用 Tab 键来补全插件名称。)

自身更新: `SPUpdate SpaceVim` 这一命令，将会打开 SpaceVim 的插件管理器，更新 SpaceVim

重新安装插件: 在插件安装、更新过程中，如果发现某个插件损坏了， 可以使用 :SPReinstall 命令进行重新安装插件。 类似于 :SPUpdate，需要添加一个插件名称参数， 可以使用 Tab 键来补全插件名称。比如： `:SPReinstall echodoc.vim`

> 由于不清楚哪些插件安装有问题,直接执行全量更新
> 在更新过程中有些软件会成功安装上
> 一些会引文插件路径污染报错

`x nvim-typescript: Updating failed, The plugin dir is dirty`

> 耐心等待,到提示 `Updated. Elapsed time: xxx sec.`
> 不然中途取消可能又会导致最初导致插件出问题相同的情况
> 接下来就处理路径污染的插件 => 找到插件的安装路径并删除对应插件文件夹
> 以 win 系统和 nvim-typescript 插件为例
> 文件在 `C:\Users\当前用户文件夹\.cache\vimfiles\repos\github.com\__mhartington\nvim-typescript`

然后就可以关闭软件,然后再次打开就会自动安装刚刚删除了的插件
