
# pip3配置国内镜像

## 修改pip的配置文件能够永久修改

1. 手动添加~/.pip/pip.conf配置文件

    ```ini
    [global]
    index-url = https://pypi.mirrors.ustc.edu.cn/simple/
    [install]
    trusted-host = mirrors.ustc.edu.cn
    ```

2. 使用命令行设置

    ```bash
    pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
    ```

## 临时使用国内pip3源

1. 在使用pip3命令时加入参数即可

    ```bash
    pip install -i https://pypi.mirrors.ustc.edu.cn/simple + name
    ```
