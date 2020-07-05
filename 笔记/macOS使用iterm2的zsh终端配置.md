# Mac终端配置方案

_主要是zsh、oh-my-zsh以及一些zsh的终端插件_

![终端展示](/Users/yangp/Library/Mobile Documents/com~apple~CloudDocs/markown/img/Mac系统使用iterm2的zsh终端配置/终端展示.png)

## 1. 安装iterm2

1. 在[iterm2](https://iterm2.com)的官网下载，放入应用程序文件夹即可

2. 安装[homebrew](https://brew.sh/index_zh-cn)

   ```bash
   /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
   ```

3. 安装[oh-my-zsh](https://ohmyz.sh)

   ```bash
   sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
   ```

   - 安装完成后，会将默认的shell修改为zsh

4. 安装[Nerd-Font](https://nerdfonts.com/)

   1. 安装Nerd-Font字体

      ```bash
      brew tap homebrew/cask-fonts
      brew cask install font-hack-nerd-font # 较慢
      ```

   2. 在iterm2中启用（注意：字体名称为Hack-Nerd-Font）

5. 安装[powerlevel10k](https://github.com/romkatv/powerlevel10k)主题

   1. 下载并安装powerlevel10k，通过git clone之后还需在zsh配置文件中启用

      ```bash
      git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
      # Set ZSH_THEME=powerlevel10k/powerlevel10k in your ~/.zshrc.
      # source .zshrc
      ```

   2. 可以通过p10k configure命令来定制powerlevel10k的主题样式

6. 安装[autojump](https://github.com/wting/autojump)

   1. 通过homebrew安装

      ```bash
      brew install autojump
      ```

   2. 用法可参照教程，懒人工作目录跳转工具

   

7. 安装和启用一些插件

   1. [syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)，命令行语法高亮

      ```bash
      git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
      ```

   2. [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions)，命令行提示

      ```bash
      git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
      ```

   3. 这些插件可以通过个人喜好启用，以上所用的插件安装后可以通过~/.zshrc文件启用和关闭

      ```shell
      plugins=(
          git
          virtualenvwrapper
          iterm2
          vscode
          man
          django
          pip
          osx
          brew
          common-aliases
          zsh-autosuggestions
          zsh-syntax-highlighting
          autojump
          encode64
          web-search
          )
      bindkey ',' autosuggest-accept # 通过，自动补齐zsh-autosuggestions的提示命令
      ```
