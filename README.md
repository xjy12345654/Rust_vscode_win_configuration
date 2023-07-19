# Rust_vscode_win_configuration

默认情况下，rustup安装在Rust目录，在c盘。可设置环境变量来改变路径！
此电脑->属性->高级系统设置->环境变量，新建两个系统变量名：RUSTUP_HOME 与 CARGO_HOME  

example:
变量名:RUSTUP_HOME   
值:  E:\development_tools\Development_environment\Rust\Rustup_home
变量名:CARGO_HOME    
值:  E:\development_tools\Development_environment\Rust\Cargo_home

再新创建 2个变量

变量名:RUSTUP_DIST_SERVER   值:  https://rsproxy.cn
变量名:RUSTUP_UPDATE_ROOT   值: https://rsproxy.cn/rustup

在自带的Path 路径上加入 %CARGO_HOME%\bin

C 盘用户目录下 （当然可能是C:\Users\xxx(其他英文名称) ）新建.cargo文件夹
新建 config文件 写入

[source.crates-io]
replace-with = 'rsproxy-sparse'
[source.rsproxy]
registry = "https://rsproxy.cn/crates.io-index"
[source.rsproxy-sparse]
registry = "sparse+https://rsproxy.cn/index/"
[registries.rsproxy]
index = "https://rsproxy.cn/crates.io-index"
[net]
git-fetch-with-cli = true

环境配置好后开始 rust安装 
采用MSVC安装工具链
地址：https://visualstudio.microsoft.com/zhhans/downloads/
注意 下载的是visual studio工具 (滚动网页到底部)

![图片1](https://github.com/xjy12345654/Rust_vscode_win_configuration/assets/38834664/5fd2aeca-bf7e-4bd8-ba10-a61932dd34de)
![图片2](https://github.com/xjy12345654/Rust_vscode_win_configuration/assets/38834664/ffdc911e-db1e-4cbd-9cbd-442a88366778)
下载安装后 点击安装c++生成工具
![图片3](https://github.com/xjy12345654/Rust_vscode_win_configuration/assets/38834664/4bc0ad47-4694-4086-929e-d04060e4731f)
![图片4](https://github.com/xjy12345654/Rust_vscode_win_configuration/assets/38834664/520bbe8a-71bf-45c8-89bb-b8b80841fa92)
开始 rust安装  
选择  安装windows msvc-64   然后选择1默认  允许修改环境 变量
输入 rustc -V ， cargo -V 查看是否安装成功

vscode 安装 rust-analyzer 插件
安装过程中vscode会额外从github上下载vscode-lldb-x86_64-windows，建议使用迅雷安装 会很快 ，下载后的报 使用离线安装

还需下载Python(3以上即可)  安装 配置环境变量 (有自动配置环境选项) 非常简单  安装第一步 勾选下方 path路径选项
debugger 
 

