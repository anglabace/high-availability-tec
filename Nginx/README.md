#### 依赖环境安装
yum -y install make zlib zlib-devel gcc-c++ libtool openssl openssl-devel

#### pcre 安装
wget ftp://ftp.csx.cam.ac.uk/pub/software/programming/pcre/pcre-8.39.tar.gz 

tar zxvf pcre-8.35.tar.gz

cd pcre-8.34

./configure

make && make install

pcre-config --prefix (查看是否安装成功)
#### nginx 安装

wget http://nginx.org/download/nginx-1.6.2.tar.gz

tar zxvf nginx-1.6.2.tar

./configure 

./configure --prefix=/opt/nginx-module --with-http_stub_status_module --with-http_ssl_module

make && make install

cd /root/svr/nginx

./sbin/nginx –t

./sbin/nginx -s reload 重新加载conf文件
#### 模块添加
wget http://wiki.nginx.org/images/7/78/Nginx_upstream_hash-0.3.tar.gz

出现的错误：error while loading shared libraries: libpcre.so.1

解决：添加软链接

ln -s /usr/local/lib/libpcre.so.1 /lib64