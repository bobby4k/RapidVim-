# rvim - RapidVim
A rapidly available version of vim configuration

## 目标
一个基于系统自带vim，快速可用的配置。 
- 使用Vim 8+ packages
- 默认安装 preservim/nerd{tree,commenter}两个插件
- 必要快捷键:
    -  \<leader\> 空格
    -  \<esc\> jj
    -  Ctrl+t 开启/关闭 nerdtree目录树窗口
    -  \<leader\>cc 注释
    -  \<leader\>cu 取消注释


### 缘由：
- 自从习惯wsl+vscode+docker，极少用vim，多年前顺手的vimrc也已丢失，遂重新配置一个快速可用的版本;
- 关于插件管理：debian自带vim不支持python，且非ide环境，仅几个插件即可，vim8的packages足矣;



