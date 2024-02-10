# Thanks to Bram Moolenaar that we have this remarkable editor, Vim.

-
-
-
-


# rvim - RapidVim
A rapidly available version of vim configuration

## 目标
一个基于系统自带vim，快速可用的配置。
- 使用Vim 8+ packages
    - 仅依赖ctags
    - 无需lua、python、nodejs支持
- 默认安装插件
    - 目录树 preservim/nerdtree
    - 代码注释 preservim/nerdcommenter
    - 老年人代码补全 neocomplcache
    - ctags增量更新 vim-gutentags
- 默认开启
    - 语法高亮 `syntax enable`
    - 代码补全(内置) `set omnifunc=syntaxcomplete#Complete`
    - ctags `set tags=tags`

### 已知问题
- 编辑vim配置文件时会产生 neocomplcache插件的set_dictionary_hel 错误
    - 临时方案 Cc 关闭 或者 :silent! TroublesomeCommand
    - 先关闭插件, 再打开vim配置文件
```shell
sed -i 's/let\ g:neocomplcache_enable_at_startup\ =\ 1/let\ g:neocomplcache_enable_at_startup\ =\ 0/' ~/.vimrc
```


### 必要快捷键:
-  \<leader\> 空格
-  \<esc\> jj
-  Ct 开启/关闭 nerdtree目录树窗口
    -  Cww 切换窗口
-  \<leader\>cc 注释
    -  \<leader\>cu 取消注释
-  Cx Co 自动补全
-  格式化与缩进
    - 向左右缩进 shift + > （或者 Shift + < ）
    - 对齐缩进 v模式,方向键 ←→↑↓ 选择, 等号键=, 对齐第一行
    - gg=G 自动格式化整个文件
- :qa 退出所有(:quitall的缩写)

## 安装
- 方式1: git clone
```jsx
    cd ~ ; mv .vimrc .vimrc_bak ; mv .vim/  .vim_bak
    git clone --recursive git@github.com:bobby4k/rvim.git .vim
    ln -sf .vim/.vimrc .vimrc

    # 更新
    cd ~/.vim
    git pull
    git submodule update --init --recursive
```

- 方式2: tar xvf
   - 下载安装包
       - [github rvim_0.1.tar.gz](https://github.com/bobby4k/rvim/releases/download/v0.1/rvim_0.1.tar.gz)
       - [gitee rvim_0.1.tar.gz](https://gitee.com/bobby4k/rvim/releases/download/v0.1/rvim_0.1.tar.gz)
```jsx
    cd ~ ; mv .vimrc .vimrc_bak ; mv .vim/  .vim_bak
    tar xvf rvim_0.1.tar.gz
    ln -sf .vim/.vimrc .vimrc
```

## ctags
- 可在存在调用关系的函数间来回跳转
### ctags插件及安装
- ctags 安装
    - debian `apt install ctags`
    - archlinux `pacman -S ctags`
    - macOS    `brew install ctags`
- vim-gutentags 增量更新插件
    - 节能

### ctags使用说明
- a. 第一次使用, **生成索引**
    - `cd your-project/ ; ctags -R *`
- b. _【可跳过】_ 设置tags路径：`:set tags=./tags,./TAGS,tags,TAGS`
    - 已使用SetTags()自动设置
        - 直接打开目录即可 `vim your-project/`
    - `echo tagfiles()` 查看当前tags文件列表
- c. **定义跳转**: 光标移动到函数或变量上，`Ctrl+]`键 跳转到定义处,  `Ctrl+o`返回
    - `Ctrl - W + ]` 用新窗口打开并查看
    - `Ctrl -W }` 使用 preview 窗口预览
- d. **查找引用**: `Ctrl+]`跳转至定义处，再次按下`Ctrl+]` 查找该函数其他引用

### 缘由：
- 自从习惯wsl+vscode+docker，极少用vim，多年前顺手的vimrc也已丢失，遂重新配置一个快速可用的版本;
- 关于插件管理：debian自带vim不支持python，且非ide环境，仅几个插件即可，vim8的packages足矣;



