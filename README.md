# 如何使用

* 一键运行脚本命令（海外用户使用）

`sh -c "$(wget -qO- https://github.com/Aceak/iSH-Tools/raw/main/iSH-Tools-Setup-CN.sh)"`

* 一键运行脚本命令（推荐访问Github困难用户使用）

`sh -c "$(wget -qO- https://mirror.ghproxy.net/https://github.com/Aceak/iSH-Tools/raw/main/iSH-Tools-Setup-CN.sh)"`

# 覆盖脚本内置变量

从 3.4 版本开始，支持覆盖脚本内置变量，让脚本适用于更多情况，以下是参数说明：

| 变量名称 | 可选项 | 注释说明 |
| --- | --- | --- |
| `HOST` | 任意网址，默认为 www.baidu.com | 用于检测网络连通性的网址 |
| `NAMESERVER` | 支持UDP查询的DNS，默认为 223.5.5.5 | 当遇到域名解析故障时替换的DNS服务器 |
| `Github_Url` | github网站，默认为 https://github.com | 从指定网站上下载iSH-Tools工具 |
| `Mirror_Url` | github镜像站，默认为 https://mirror.ghproxy.com/https://github.com | 用于加速github访问 |
| `Mirror_Repo` | 默认替换的镜像源，默认为 http://mirrors.tuna.tsinghua.edu.cn | 用于加速apk源访问 |
| `Bypass_Check` | 1：跳过网络&地区检查、Net：只跳过网络检查、Loc：只跳过地区检查，默认为 0 都不跳过| 跳过脚本内置检测功能 |
| `Dev_Mode` | 1：开启开发者模式。允许在非iSH的Alpine下运行，默认为 0 不开启 | 用于在其他Alpine下使用 |

## 例子
``` 
# 跳过全部检测
Bypass_Check=1 iSH-Tools

# 只跳过 网络连接检测
Bypass_Check=Net iSH-Tools

# 进入开发者模式 (在iSH里不会有效果)
Dev_Mode=1 iSH-Tools

# 让变量长久生效 (本次会话中有效)
export Bypass_Check=1

# 让变量自动生效，以ash为例子
echo "export Bypass_Check=1" >> ~/.profile
```



