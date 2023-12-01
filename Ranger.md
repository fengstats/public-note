## 说明

基础操作方式与 Vim 相同（作者貌似是受 Vim 模式启发才有的 ranger）

![](https://cdn.jsdelivr.net/gh/fengstats/blogcdn@main/2023/Ranger-%E7%9B%AE%E5%BD%95%E4%BF%A1%E6%81%AF.png)

- commands.py：一些命令函数，可供其他文件（`rc.conf`）调用执行
- commands_full.py：所有命令
- rc.conf：配置键位命令映射
- rifle.conf：文件关联（设置文件打开的程序）
- scope.sh：文件的预览方式

## 常用指令

|  命令   | 功能说明                                                                                                               |
| :-----: | :--------------------------------------------------------------------------------------------------------------------- |
| \<c-r\> | 重新加载当前目录（一般用于选中部分文件后取消选中状态）|
|   zh    | 显示隐藏文件（`backspace`：退格键也可以）|
|   yp    | 复制当前文件/目录的路径                                                                                                |
|   `/`   |在当前位置进行搜索|
|    f    | 过滤搜索，只显示匹配结果，使用 Tab 切换（**自定义**）|
|  zf/zz  | 基本与 f 一致，值得注意的是：使用命令后不符合条件的文件/目录会被隐藏，需要重新执行 `zf/zz`（不加任何条件即可恢复显示）|
|   s/S   | 使用 shell 控制台命令 / 打开当前光标所在路径 shell                                                                     |
|   cw    |文件重命名|
|  I/A/a  | 保留原有名称，光标移动至文件名称开头/结尾（`a`：不包含后缀）|
|   V/M   | 新建文件/目录（**自定义**）|
|   dd    | 剪切文件/目录                                                                                                          |
|   yy    | 复制文件/目录                                                                                                          |
|   pp    | 粘贴文件/目录                                                                                                          |
|   DD    | 删除文件/目录（**自定义**，不需要二次确认，会移动到废纸篓）|

## 不常用

| 命令  | 功能说明                                                                    |
| :---: | :-------------------------------------------------------------------------- |
|  uu   | 取消剪切（**自定义**，默认是 `ud`）|
|  uv   | 取消选择                                                                    |
|   r   | 对文件执行命令，有相对应的选项（`open` 可以打开访达）|
|  C/X  | 压缩/解压文件（**自定义**，注意压缩要写扩展名，解压前需要 `yy` 复制压缩包）|
|   w   | 进入任务管理器，`dd` 可以停止任务，`q` 退出                                 |
|  yn   | 复制当前文件/目录的名称                                                     |
|  y.   | 复制当前文件/目录的名称，去除文件后缀                                       |
|  dD   | 删除文件/目录，需要二次确认，会直接删除，不会移动到废纸篓                   |
| \[/\] | 上一层（父级）目录上下切换                                                  |
|  H/L  | 前进/后退进入过的目录                                                       |