# 常见问题

1.本地测试正常，上传到服务器提示找不到模块？

请确认服务器是否开启 PATH_INFO，如果未开启，请先开启。
如果您的服务器不支持 PATH_INFO，那请使用兼容模式访问。如：
?s=/模块/控制器/操作/[参数名/参数值...]
详细请查阅 [ThinkPHP文档](http://www.kancloud.cn/manual/thinkphp5/118012 "ThinkPHP文档")

------------

2.在 lnmp 环境下，首页显示空白？

请查看 php.ini 中的 disable_functions 是否禁用了 scandir 函数。如果是，请删除 scandir，然后重启 php 服务。
检查目录是否可写，扩展是否安装。

------------

3.后台页面响应时间过长？

全新安装框架，打开后台，页面响应过长，要好几秒才能完全加载页面？
尝试将配置文件`\application\database.php`中的`'hostname' => 'localhost'`改为`'hostname' => '127.0.0.1'`

------------

4.微信支付证书路径如何设置？

微信支付证书的路径必须使用绝对路径，否则会报错。