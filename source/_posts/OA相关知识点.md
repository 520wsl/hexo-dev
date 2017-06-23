---
title: OA相关知识点
categories:
- 工具
- 安装教程
tags:
- OA
- PHP
- Git
- Visual Studio 2013
- Nginx
- Eclipse
- Idea
- AvalonJS
---
# 工具
## ==Visual studio 2013==  .Net 代码编写
## ==[eclipse]((https://www.eclipse.org/downloads/download.php?file=/oomph/epp/neon/R3/eclipse-inst-win64.exe))== ([idea](http://www.jetbrains.com/products.html?fromMenu#lang=php-lang))  PHP版  UI2代码编写
## ==[Git](https://git-scm.com/) 代码提交==  版本控制
- [git参考资料](http://note.youdao.com/noteshare?id=58e9b02ac9117dfd0b0b63bcbb133196&sub=61007728B1854529AADF618A1DF82B32) 

## [josn格式化](http://json.cn/)
---
# 环境

## [Nginx](http://nginx.org/)
- RunHiddenConsole 下载   配置  star.bat stop.bat
---
- nginx-1.10.1\conf\nginx.conf
```

worker_processes  30;

events {
    worker_connections  1024;
}


http {
	include       mime.types;
	default_type  application/octet-stream;

	sendfile        on;
	keepalive_timeout  30;
	fastcgi_connect_timeout 30;
	fastcgi_read_timeout 30;
	fastcgi_send_timeout 30;
	client_max_body_size 1500M;
	
	# 项目配置
	server {
		listen		6001;
		server_name	172.30.34.114;


		location / {
			root	F:/GIT/OAGIT/OAUI2/OAUI2;
			index	index.html index.htm index.php;
			#访问路径的文件不存在则重写URL转交给ThinkPHP处理  
			if (!-e $request_filename) {  
			   rewrite  ^/(.*)$  /index.php/$1  last;  
			   break;  
			}  
		}

		error_page   500 502 503 504  /50x.html;

		location = /50x.html {
			root   F:/GIT/OAGIT/OAUI2/OAUI2;
		}

		location ~ \.php {
			root		F:/GIT/OAGIT/OAUI2/OAUI2;
			fastcgi_pass	127.0.0.1:9000;
			fastcgi_index	index.php;
			#加载Nginx默认"服务器环境变量"配置  
			include        fastcgi.conf;  
			  
			#设置PATH_INFO并改写SCRIPT_FILENAME,SCRIPT_NAME服务器环境变量  
			set $fastcgi_script_name2 $fastcgi_script_name;  
			if ($fastcgi_script_name ~ "^(.+\.php)(/.+)$") {  
			    set $fastcgi_script_name2 $1;  
			    set $path_info $2;  
			}  
			fastcgi_param   PATH_INFO $path_info;  
			fastcgi_param   SCRIPT_FILENAME   $document_root$fastcgi_script_name2;  
			fastcgi_param   SCRIPT_NAME   $fastcgi_script_name2;  
		}
	}
	
	# 代理配置
	#OA
	server {
		listen       6002;
		server_name  172.30.34.114;
		#oaold
		location / {
			proxy_pass http://172.30.34.114:8003;
		}
		#UI2
		location /ui2 {
			proxy_pass http://172.30.34.114:6001/;
		}
		
		#图片
		location /oatest {
			proxy_pass http://192.168.0.8:21521/;
		}
		
		
	}
}

```
## [mysql]()
---
## [sqlserver]()
---
## iis
---
## [PHP](http://windows.php.net/download#php-5.6)
### 配置  
- extension_dir  ext文件夹路径  案例：`extension_dir = "D:/php-5.6.13-Win32-VC11-x64/ext"`
- 扩展模块
```
extension=php_bz2.dll
extension=php_curl.dll
;extension=php_fileinfo.dll
extension=php_gd2.dll
;extension=php_gettext.dll
;extension=php_gmp.dll
;extension=php_intl.dll
;extension=php_imap.dll
;extension=php_interbase.dll
;extension=php_ldap.dll
extension=php_mbstring.dll
;extension=php_exif.dll      ; Must be after mbstring as it depends on it
extension=php_mysql.dll
extension=php_mysqli.dll
;extension=php_oci8_12c.dll  ; Use with Oracle Database 12c Instant Client
;extension=php_openssl.dll
;extension=php_pdo_firebird.dll
extension=php_pdo_mysql.dll
;extension=php_pdo_oci.dll
;extension=php_pdo_odbc.dll
;extension=php_pdo_pgsql.dll
;extension=php_pdo_sqlite.dll
;extension=php_pgsql.dll
;extension=php_shmop.dll

; The MIBS data available in the PHP distribution must be installed. 
; See http://www.php.net/manual/en/snmp.installation.php 
;extension=php_snmp.dll

extension=php_soap.dll
extension=php_sockets.dll
;extension=php_sqlite3.dll
;extension=php_sybase_ct.dll
;extension=php_tidy.dll
;extension=php_xmlrpc.dll
;extension=php_xsl.dll
```
- 时区
```
[Date]
; Defines the default timezone used by the date functions
; http://php.net/date.timezone
date.timezone = 'PRC'
```

---
# 接口
- 有道云 markdown
- [RAP](http://192.168.2.200:8081)

---
# 开发代码
# OAOld
### 目录指定到 4.c
### 添加   LitJSON.dll   路径  ： OAOld\4.c\bin

---
# OAUI2
## [thinkPhp3.2](https://www.kancloud.cn/manual/thinkphp/1678)
## [avalonjs](http://avalonjs.coding.me/directive.html)
## [josn格式化](http://json.cn/)
## 服务地址：`OA2 => 'http://172.30.34.114:9002'