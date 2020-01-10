1.运行 fdisk -l 命令查看数据盘f

2.运行 fdisk /dev/xvdb，对数据盘进行分区。根据提示，依次输入 n，p，1，两次回车，wq，分区就开始了。

3.运行 fdisk -l 命令，查看新的分区。新分区 vdb1 已经创建好

4.运行 mkfs.ext3 /dev/xvdb1，对新分区进行格式化。
命令解释：mkfs可以理解为make file system，即设置硬盘文件格式

5.创建一个 文件夹 mkdir www

6.运行 echo /dev/vdb1 /www ext3 defaults 0 0 >> /etc/fstab 写入新分区信息

/mnt命令解释： 表示将该硬盘挂载到www目录下，同理将www更改为xxx，则可以将数据盘挂载到xxx目录下

7.完成后，可以使用 cat /etc/fstab 命令查看。

8.运行 mount /dev/vdb1 /www 挂载新分区，然后执行 df -h 查看分区

