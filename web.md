第一关 view_source  
![png]()  
场景为：  
![png]() 
鼠标无法用，我们直接F12查看源代码，发现flag  
![png]() 
  
  
第二关 robots  
![png]() 
场景为：  
![png]() 
发现网页是空白的，转到robots.txt页面下看看，发现flag  
![png]() 
  
  
第三关 backup  
![png]() 
场景为：  
![png]() 
index.php的备份文件名为：index.php.bak,直接下载即可  
![png]() 
  
  
第四关 cookie  
![png]() 
场景为：  
![png]() 
F12查看一下cookie，发现有个cookie.php,进入后F12得到flag    
![png]() 
  
  
第五关 disabled_button  
![png]() 
场景为：  
![png]() 
有个flag按钮但是点不了，F12发现按钮处有个disabled属性，这个属性可以设置是否禁用单选按钮，删掉后按钮可点  
![png]() 
  
  
第六关 weak auth  
![png]() 
场景为：  
![png]() 
是个登录页面，先试着用万能密码绕过试下  
![png]() 
绕过失败，显示登录名为admin  
![png]() 
可以用burpsuit抓包爆破密码试试  
![png]() 
![png]() 
![png]() 
  
  
第七关 simple_php  
![png]() 
场景为：  
![png]() 
其中有个函数is_numeric()，用于检测变量是否为数字或数字字符串。  
构造http://124.126.19.106:xxxx/?a=0x&b=1235x  
![png]() 
  
  
第八关 get_post  
![png]() 
场景为：  
![png]() 
按网页提示内容作即可  
![png]() 
![png]() 
![png]() 
![png]() 
  
  
第九关 xff_referer  
![png]() 
场景为：  
![png]() 
要求ip为123.123.123.123，brupsuit抓包，修改X-Forwarded-For为123.123.123.123并提交  
![png]() 
页面显示必须来自谷歌，所以修改Referer为https://www.google.com 再次提交  
![png]() 
  
  
第十关 webshell  
![png]() 
场景为：  
![png]() 
题目明确一句话在index.php下，直接用菜刀连接  
![png]() 
  
  
第十一关 command execution  
![png]() 
场景为：  
![png]() 
常见命令执行有以下几个：  
command1 & command2 ：先执行command2后执行command1  
command1 && command2 ：先执行command1后执行command2  
command1 | command2 ：只执行command2  
command1 || command2 ：command1执行失败，再执行command2(若command1执行成功，就不再执行command2)  
依次尝试进行ping命令，找到home文件夹下的flag.txt  
![png]() 
![png]() 
![png]() 
![png]() 
![png]() 
![png]() 
![png]() 
  
  
第十二关 simple_js  
![png]() 
场景为：  
![png]() 
随便输入密码，弹窗关闭后F12  
![png]() 
将源代码中数字复制，十六进制转换成ascii码后发现还是数字，继续用十进制转换成ascii码后成功获得flag
