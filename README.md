# AntiFrida
原文https://github.com/b-mueller/frida-detection-demo

（1）frida-server通过 TCP 对外与 frida 通信， Java 遍历运行的进程列表能够检查到 frida-server 是否在运行 
（2）frida-server 默认的TCP 端口是 27047，检查端口是否开放 
（3）frida-server 使用 D-Bus 协议通信，为每个开放的端口发送 D-Bus 的认证消息，回复的端口是 frida-server 
（4）利用frida 运行时映射到内存的库，直接逐一检查加载的库。在内存中扫描 frida 的库特征 “gadgets”。例如：字符串 “LIBFRIDA”，它在所有 frida-gadget 和 frida-agent 的版本中都有出现 
