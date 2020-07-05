# Mac通过PD虚拟机安装Ubuntu



## 虚拟机安装

- 通过虚拟机软件自带的ubunut镜像可以直接安装系统，原始版本为英文版，目前镜像版本为18.04TLS

- 安装速度较快，安装完成之后安装虚拟机工具，基本可以完美配饰

  _注意：要尽可能的少使用gnome extension插件_

  

## 更新与软件安装

- 首先，需要将ubunut的默认更新源更改为国内，eg：阿里源、中科大、南京大学

- 更新系统，更改语言和时区

- 安装常用软件，因为在虚拟机中所以需要尽可能少的安装无用的软件

- Typora安装

  ````bash
  sudo apt-get install typora
  ````

- 安装shadowsocks工具及配置

- 安装proxychains4终端代理工具

- 安装中文输入法：ibus-rime

## 优化及界面美化

- 安装gnome-tweak-tool
- 安装monaco字体
- 安装GKT3主题
- 安装图标主题
- 安装gnome-shell主题
- 安装gnome-extensions拓展包，但是不能开启其他的拓展

## 配置

- 配置vim编辑器
- 配置rime输入法
- 配置Term终端配色
- 卸载一些无用的软件，减少磁盘空间（可以通过软件中心卸载）