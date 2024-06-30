## 检索过滤和内容重定向

# 查找
- which返回程序搜索结果，即添加到环境变量的程序（注意大小写）
- find指令
  ```bash
  find (地址) -type f(查找普通文件类型) -name (不加引号，可以用*等通配符) -user (指定用户) -size +20k -size -28k -newermt 2020-03-03 -exec ls -al {} \; 2>/dev/null(舍弃错误输出)
  
  对于-exec ls -al {} \; 的作用
  exec：find 命令的一个选项，允许对找到的每个文件执行指定的命令。
  ls -al：列出文件的详细信息，包括权限、所有者、文件大小、修改时间等。
  {}：占位符，表示当前找到的文件。
  \;：表示 -exec 命令的结束。
  ```
- 占位符 {}
  作用：占位符 {} 用于代表 find 命令找到的每一个文件或目录。在 -exec 选项中，{} 会被当前找到的文件或目录替换。
  必要性：通过使用 {}，可以将找到的每个文件作为参数传递给指定的命令。例如，在 -exec ls -al {} \; 中，{} 将被找到的每个文件的路径替换，ls -al 将对每个文件执行。
- 结束符 \;
  作用：结束符 \; 用于指示 find 命令的 -exec 选项的结束。这意味着命令部分在此处结束。
  必要性：命令行中的 ; 是一个特殊字符，在命令行中有特定的含义。如果直接使用 ;，会被shell解释为命令分隔符。通过在 ; 前添加反斜杠 \，可以将其转义，使得 find 命令正确识别并处理 -exec 选项的结束。


- locate指令
  ```bash
  更快地检索，但是更少的可选项
  sudo updatedb
  locate *.conf
  ```


# 文件流
- 流的类型编号：0输入 1输出 2错误
- cat指令：先获取输入流，将其转移到输出流
- /dev/null作为数据垃圾站，可以导入以舍弃错误流
- 实际案例：
  ```bash
  编号 > /dev/null
  编号 > /dev/null >result.txt
  就像水坝一样，一段信息流先将2给devnull拦截，剩下的信息流入result.txt
  
  一样的，也可以将2和1分别写入不同文件
  >将会覆盖文件，而>>会附加在文件结尾
  
  < my.txt  将把文件作为输入流
   cat << EOF > stream.txt
   
   这个指令会将我的每个输入添加上eof以截断一次输入（按下enter）,cat接收输入，再将其作为输出，输出给txt文本，显然<<作为附加而不是覆盖的意义是非常明显的
  ```
- *实用工具wc
  ```bash
  black2o1@htb[/htb]$ find /etc/ -name *.conf 2>/dev/null | grep systemd | wc -l
  
  wc将会按行统计结果
  ```
  
  
# 内容过滤
- grep
  ```bash
  grep -v 排除
  grep -i 不区分大小写black2o1@htb[/htb]$ find /etc/ -name *.conf 2>/dev/null | grep systemd | wc -l
  ```
- cut 
- tr
- column
- awk
- sed
- wc
  ```bash
  待补充
  ```
  

