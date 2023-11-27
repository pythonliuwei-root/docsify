# NGINX

## Nginx的应用场景

它是一个高性能的反向代理和web服务器管理软件，因其系统的资源消耗低、运行文档且具有高性能的并发处理能力等特性，nginx在互联网中起到非常广泛的使用。

## Nginx的特点

* 高性能、高并发
* 扩展性好
* 异步非阻塞的事件驱动模型
* 应用场景
  * HTTP服务器
  * FTP服务器
  * 反向代理
  * 负载均衡

nginx 高并发支持 单击能够支持10w+的并发连接（取决于内存大小，极限能够百万），那么在实际生产中也是非常能接近这个数字的，这取决于nginx在linux环境下使用了epolllo多路复用模型

nginx 内存消耗低 在同类型web服务中，nginx比apache占用的内存资源更少，在一般情况下10k非活跃的http Keep-Alive连接在nginx中仅消耗2.5m内存

nginx 高扩展性 低耦合的模块设计并且有丰富的第三方模块支持

nginx 高可靠性 经过十几年各种复杂场景和各大公司的生产环境验证，并且nginx的架构是由master进程和worker进程组成的。如果worker进程出现问题，那么master进程可以快速开启一个新的worker进程提供服务。

## 在ubuntu上安装nginx

1. 先升级apt

   apt upgrade -y

   apt update -y

2. 安装nginx

   apt install nginx -y

3. 检查nginx是否运行

   systemctl status nginx

4. 设置服务器重启后nginx也启动

   systemctl enable nginx

#### 检查nginx的配置信息

​	nginx -t

#### 刷新nginx的配置信息

​	nginx -s reload

#### 停止nginx服务

​	nginx -s stop

#### 优雅停止nginx服务

​	nginx -s quit

### 设置nginx配置文件防盗链效果

```nginx
server{
	listen 9999;
    server_name localhost;
    location ~* .*\.(gif|jpg|png)${
        root /opt/test/img/;
        valid_referers none blocked taobao.com;
        if($invalid_referer){
            #return 403;
            rewrite ^/ http://1.1.1.1:9999/eror.webp;
            break;
        }
    }
}
```

#### 反防盗链方法

```html
在index.html创建数据
<html>
    <header>
        <meta name="referrer" content="no-referrer"></header>
    </header>
</html>
```

### Nginx配置开启GZIP压缩

网站的访问速度是用户在访问网站的过程中非常重要的一步，网站的访问速度是由很多因素影响的，网络的带宽、客户端的带宽、访问资源的大小。我们服务器的带宽是开发者和部署者决定不了的，客户端的带宽也是决定不了的，唯一能让开发者和部署者设置的就是访问资源的大小。通过GZIP压缩的方式，让访问速度提高！

gzip压缩针对文本文件非常好，但是针对图片、音频、视频文件就不是非常的好用了。

```
server{
	gzip on;
	gzip_types application/javascript application/json;
	gzip_static on;
	gzip_vary on;
	gzip_comp_level 5;
	gzip_buffers 16 8k;
	gizp_min_length 1k;
	gzip_http_version 1.1;
}
```

#### 参数详解

| 名称              | 参考参数              | 详解                                                         |
| ----------------- | --------------------- | ------------------------------------------------------------ |
| gzip              | on                    | 是否开启gzip压缩(on开启 off关闭)                             |
| gzip_min_length   | 1k                    | 最小压缩单位，小于1k压缩意义就不大了                         |
| gzip_comp_level   | 6                     | 压缩级别，1-9可选，数字越大压缩效果越好，但是会加大cpu压力，高并发场景不建议调的太高 |
| gzip_types        | js、css、text、json等 | 压缩类型，取自application/type,文本文件压缩的效果最好        |
| gzip_very         | on                    | 用在响应头添加very:accept_encoding,让代理服务器根据请求识别是否启动了gzip压缩 |
| gzip_http_version | 1.1                   | 启动gzip压缩的最低http协议版本，这里也可以不填，默认就是1.1  |
| gzip_buffers      | 2 4k                  | 设置压缩所需要的缓冲区大小，以4k为单位，如果文件为7k则申请2*4k的缓冲区 |
| gzip_static       | on                    | 静态压缩，也就是提前已经准备好了压缩文件在同目录下会有一个.gz的压缩包，避免了动态压缩性能较好。 |
| gzip_disable      | MSIE[1-6]\\.          | 设置禁用浏览器进行GZIP压缩，IE6的某些人版本对gzip的压缩支持很不好，会造成页面的假死 |

### Nginx开启Brotli压缩

#### 原理

通过LG77算法、后面附编码、二阶文本建模的方式来进行数字压缩，它比gzip压缩高出18%-25%左右，它能带来更好的加载速度。IE浏览器是不支持brotli压缩算法的，brotli压缩和gzip压缩是可以在nginx中共存的，brotli压缩只支持https协议，不支持http协议。

#### 下载nginx的brotli算法

```shell
git clone https://github.com/google/ngx_brotli.git
```

#### 进入到brotli的执行目录

```nginx
cd ngx_brotli/deps
```

#### 执行brotli算法

```shell
git submodule update --init
```

#### 切换到nginx的主目录，添加brotli压缩算法的路径

```shell
cd nginx
./configure --prefix=/opt/nginx --with-http_ssl_module --add-module=/opt/nginx_brotil
```

#### 替换nginx文件

#### 配置文件调整

```
http{
	brotli on;
	brotli_static on;
	brotli_types allication/atom+xml application/javascript application/json application/vnd.ms-fontbject application/x-font-opentype application/x-font-ttf application/x-javascript text/javascript text/plain text/xml image/x-icon image/x-win-bitmp text/css;
	#压缩级别 0-11 默认是6
	brotli_comp_level 6;
	#窗口设置， 可支持 1k 2k 4k 8k 12k 32k 
	brotli_window 1k;
	#设置压缩最小单位
	brotli_min_length 20;
}
```

### 反向代理实现免备案域名访问

#### Nginx反代实现免备案域名访问原理

![image-20231127151613022](C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\image-20231127151613022.png)

```
server{
	listen 80;
	server_name tuling.xxx.com;
	location /{
		proxy_pass http://1.1.1.1;
	}
}
```

#### 重载nginx配置文件

```
nginx -s reload
```

### Nginx配置开启HTTPS证书

https的目的是提供对网站服务器的身份验证，保护交换资料的隐私和完整性。

```
server{
	listen	443 ssl;
	server_name xxxx.com;
	ssl_certificate /home/nginx/ssl/xx.pem;
	ssl_certificate_key /home/nginx/ssl/xx.key;
	ssl_session_cache shared:SSL:1m;
	ssl_session_timeout 5m;
	ssl_ciphers HIGN:!aNULL:!MD5;
	ssl_prefer_server_ciphers on;
	location / {
		root html;
		index index.html index.htm;
	}
}
```

### 重定向到域名

如果用户以ip地址访问80端口，将它重命名到域名访问

```
server{
	listen	80;
	server_name xxx.com;
	rewrite .* https://$serve_name$1 redirect;
}
```

## nginx开启限流

通过限流手段保证服务正常运行

漏桶算法和令牌桶算法

### 请求限流

语法

```
limit_req zone=name [burst=number] [nodelay | delay=number];
默认值 -
上下文 http, server, location
```

案例

```
limit_req_zone $binary_remote_addr zone=ip_limit:10m rate=1r/s;
```

参数一：`$binary_remote_addr`表示通过remote_addr这个标识来做现职，限制是同一客户端IP地址，在这里，客户端IP地址作为关键，请注意,不是`$remote_addr`而是使用`$binary_remote_addr`变量。`$ remote_addr`变量的大小可以从7-15个字符不等，存储的状态在32位平台上始终占用32或64字节，在64位平台上占用64字节。一个兆字节的区域可以保持大约32000个32字节的状态或大约16000个64字节的状态。如果区域存储耗尽，服务器会将错误返回给所有其他请求。

参数二：`zone=ip_limit:10m`表示生成一个10M大小的名字为`ip_limit`的内存区域，主要用来存储访问的频次信息

参数三:`rate=1r/s`表示允许相同标识客户端的一个访问频次，1r的意思就是1次

```
limit_req zone=ip_limit burst=5 nodelay;
```

参数一：`zone`表示使用哪个区域来做限制，这里与上面一样

参数二：`burst`爆发的意思，这个配置的意思是设置一个大小为5的缓冲区，当有大量请求（爆发）过来时，超过了访问频次限制的请求可以先放在这个缓冲区内。

### 连接限流

语法

```
limit_conn zone number;
默认值 -
上下文 http, server, location
```

案例

```
limit_conn_zone $binary_remote_addr zone=addr:10m;
```

参数一：`$binary_remote_addr`表示通过remote_addr这个标识来做限制，限制的是同一个客户端ip地址

参数二：`zone=ip_limit:10m`表示生成一个10m大小的名称为ip_limit的内存区域，主要用来存储访问的频次信息

```
limit_conn addr 1;
```

参数一：`zone`表设计使用那个区域来做限制，这里与上面一样

参数二：表示相同标识客户端的一个访问频次，这里的1代表只允许每个ip地址1个连接

```

http{
	limit_conn_zone $binary_remote_addr zone=conn_limit:10m;
}
```

### Nginx配置合并请求

多个文件作为一次请求，目的减少连接数量

#### 下载三方模块包

```
git clone https://github.com/alibaba/nginx-http-conncat.git
```

```
./configure --prefix=/opt/nginx --with-http_ssl_module --add-module=/opt/nginx_brotil --add-module=/opt/nginx-http-conncat
```

#### 配置参数

```
server{
	concat on;
	concat_max_files 20;
	concat_unique off;
	concat_types text/css application/javascript;
	concat_delimiter '\n';
	concat_igore_file_error on;
}
```

