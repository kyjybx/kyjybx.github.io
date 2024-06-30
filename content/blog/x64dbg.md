-  f2 添加断点（软件断点：内存表现为cc）
- show mnemonic brief 对汇编指令说明（f1）
- f7 跳入
- f8 跳过
- f9 开始执行，直到断点
- 可将dump的内存转义为汇编
- ctl + g向指定地址跳转
- ctl + f1 查看指令文档
- ctl + b 检索
- ctl + * 设置rip
- \* 跳转到rip
- ctl + p patch
- 

- bp + VirtualProtect (或者其他指令) 在指定系统api断点（也可以用来检索系统api位置）
- 硬件断点：适用于软件断点无法工作时,硬件断点储存在寄存器中，所以数量有限
  ```x64dbg
  bphws VirtualAlloc
  ```
- disasm.sel()获取地址？（反汇编界面）
- dump.sel (内存界面，当前地址)
- rcx = ...修改寄存器
- windows internals
- ir.team
- vx underground
pefile formats
reflective file loading
malecore
mepedia