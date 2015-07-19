# Typecho2Hexo Python版小工具
准备从 Typecho 转到更加轻量的 Hexo。但是没找到什么好用的到处工具，github 上有一版 PHP 的，但是没有分类、tag等东西，只能自己动手了，此类小工具自然是 Python 比较方便~  
  
简陋暴力，从数据库中直接拿出相关信息生成对应文件，包含文章、分类、标签，由于我没用过二级分类~ 所以没支持...

####测试环境
Typecho :

	 1.0 (14.10.10)
	 
Hexo :

	hexo-cli: 0.1.7
	os: Darwin 14.4.0 darwin x64
	http_parser: 2.3
	node: 0.12.6
	v8: 3.28.71.19
	uv: 1.6.1
	zlib: 1.2.8
	modules: 14
	openssl: 1.0.1o

操作系统及运行环境 ：

	OSX 10.10.4
	Ubuntu 15.04	
	Mysql 5.6
	Python 2.7.6
	
	
####使用方法
默认程序和数据库在同一台服务器，如不是请修改host，更改相关的数据库名称，数据库账号和密码。
在当前目录下执行

	python Typecho2Hexo.py
	
生成 data 文件夹（包含所有数据）， 把文件夹内所有的文件拷贝到 Hexo 的 source 目录下， 重启 Hexo Server 即可。

####相关依赖 
直接依赖了一些自己平时常用的包~~（懒）

	torndb #数据库连接
	arrow #时间的相关操作
	
	
####其他
发现一些小坑， 比如你的文章内如果出现 {% %} 这些内容的话 Hexo 服务就出问题，因为语法冲突~  
简单的办法是 在这样的地方套上  {% raw %} xxx {% endraw %} ... 问题就是其中的内容会全部丢失样式。