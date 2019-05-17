## 广播
1. 在每个进程注入自己的广播（InspeckageReceiver）
2. 解析http收到的请求通过发送广播，然后对应的app执行

1. 自己app注入广播 InspeckageWebReceiver（需要结果返回的 比如 文件树 剪切板 检查app是否允许 ）
2. 实现思路是：接收数据存储转到InspeckageReceiver处理（或直接处理），然后把结果交给到InspeckageWebReceiver，存入SharePresence（不需要注入的进程）

## 服务
1. 有两个Server 为LogService和InspeckageWebReceiver，
2. 功能分别对应是webSock传递日志 和http传递数据（在服务里面简历webSock或http连接）

## hook
在hook包里就是核心功能，hook app的数据


## 技术
1. NanoHttpd开源库(手机上搭建服务端)
2. hook&xposed
3. html/js/css
4. webSock
5. android
