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
- 默认安装 preservim/nerd{tree,commenter}两个插件
    - 语法高亮 syntax enable
    - 代码补全 set omnifunc=syntaxcomplete#Complete
- 增加老版本代码补全neocomplcache 
    - 无需lua、python、nodejs支持
    - 编辑vim配置文件时会产生 set_dictionary_hel 错误
        - Cc 关闭 或者 :silent! TroublesomeCommand
        - :NeoComplCacheDisable 临时关闭该插件



### 必要快捷键:
    -  \<leader\> 空格
    -  \<esc\> jj
    -  Ct 开启/关闭 nerdtree目录树窗口
        -  Cww 切换窗口
    -  \<leader\>cc 注释
        -  \<leader\>cu 取消注释
    -  Cx Co 自动补全 
    - :qa 退出所有(:quitall的缩写)

## 安装
- 方式1: git clone 
```jsx
    cd ~ ; mv .vimrc .vimrc_bak ; mv .vim/  .vim_bak
    git clone --recursive git@github.com:bobby4k/rvim.git .vim
    ln -sf .vim/.vimrc .vimrc
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
    

### 缘由：
- 自从习惯wsl+vscode+docker，极少用vim，多年前顺手的vimrc也已丢失，遂重新配置一个快速可用的版本;
- 关于插件管理：debian自带vim不支持python，且非ide环境，仅几个插件即可，vim8的packages足矣;



