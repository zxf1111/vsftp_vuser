# vsftp_vuser





今天安装vsftp服务器，在修改了 chroot_local_user 属性以后，发现进行客户端访问的时候会报错：500 OOPS: vsftpd: refusing to run with writable root inside chroot()
到网上查了资料,得到解决问题方法如下：
"如果启用chroot,必须保证ftp根目录不可写,这样对于ftp根直接为网站根目录的用户不方便,所以建议假如ftp根目录是/home/${cjh},则将访问权限改写如下
chmod a-w /home/cjh
