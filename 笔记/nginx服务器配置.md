# 个人服务器配置

## 通过在nginx中使用多个站点配置不同的应用

1. 安装nginx、php-fpm

   ```bash
   sudo apt install nginx php-fpm
   ```

2. nginx和php常用命令

    ```bash
    sudo service nginx start/stop/restart/reload
    sudo nginx -t
    sudo ln www.yangp1205.cn.conf www.yangp1205.cn
    sudo nginx -s reload
    sudo service php-fpm7.2 start/stop/restart ```

3. 在配置不同的站点时只需要在服务器商端讲不同的主机地址都解析到主机的IP地址即可，不同的主机地址可通过server_name的不同来区分
4. 在ubuntu上主要配置Wordpress和owncloud即可

## 配置终端界面

1. 安装zsh

   ```bash
   sudo apt install zsh
   ```

2. 安装oh-my-zsh
3. 安装zplug
4. 配置zplug和oh-my-zsh

## 配置vim编辑器插件

- *使用vim-plug插件管理器*

1. 安装vim-plug，使用git
2. 配置.vimrc文件导入vim-plug
3. 插件安装
   - 自动补齐符号插件
   - 自动调整python编码规范
   - vim开始界面
   - 目录文件书
   - 代码块
4. 文件自动署名
