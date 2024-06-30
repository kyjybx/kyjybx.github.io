## linux说明_vol1

##  网络问题
- 在连htb靶场时的openvpn,用nc，ssh,或者各种网络工具时的报错，首先考虑权限问题
- htb靶场的ssh远程连接需要同时运行在所提供的vpn开启的状态下才会正常连接
- 如果连接失败，应当主动sudo pkill以结束进程（实验证明关闭窗口进程不会终结）
- 


## 进程检查
- 根据指定关键字检索进程的指令
  ```bash
  ps -ef 按照完整格式输出全部进程，绝大多数情况下和 -aux一样，因为只是输出规范不同
  使用grep过滤（注意grep查询进程也会包含在内）
  | grep "openvpn"
  ```
  
  针对服务属性进程使用systemctl检索
  
- 启动，终止，检查（systemctl）
  ```bash
  启动服务：
  systemctl start Myservice
  
  确认状态：
  systemctl status Myservice
  
  检查所有运行的服务：
  systemctl list-units --type=service
  
  任务移交后台执行（有待实验）：
  1.任务指令后添加&
  2.使用ctl+z暂停，输入bg以转入后台
  3.根据jobs查询的后台进程编号，使用fg 编号 拉回前台
  
  检查后台运行进程:
  jobs     (只会显示当前shell对话下启动的进程信息)
  ```
  
  
## 多命令执行
```bash
   ;    分隔执行
   &&   任何一个错误执行都会断开
   |    不仅需要正确执行，还要求类型匹配
   
   linux的执行顺序为从左到右
```


## 网络
- curl + url ：将当前当前页面html原始文件展示在终端
- wget + url : 将网站下载至本地
- 服务器相关待补充


## 文件服务
- touch/nano 可以创建新文件
- mkdir可以创建新文件夹
- mkdir -p 可以创建指定路径
- 使用.可以标注为当前节点，例如mkdir -p ./haha/hahah
- *有用的指令 tree 指定文件夹 可以展示文件结构


# _文件移动_
- 移动指令：mv
  ```bash
  重命名文件：
  mv my.txt rename.txt
  
  linux支持将指定文件移动的同时，将文件重命名
  mv my.txt rename.txt Newdir/
  ```
# _文件复制_
- 复制指令：cp
  ```bash
  cp Mydir/my.txt Storage/local/
  ```
  
  