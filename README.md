# docker
## Docker run 命令
docker run ：创建一个新的容器并运行一个命令 <br>
**语法** <br>
docker run [OPTIONS] IMAGE [COMMAND] [ARG...] <br>
**PTIONS说明：** <br>
* -a stdin: 指定标准输入输出内容类型，可选 STDIN/STDOUT/STDERR 三项； <br>
* -d: 后台运行容器，并返回容器ID； <br>
* -i: 以交互模式运行容器，通常与 -t 同时使用； <br>
* -t: 为容器重新分配一个伪输入终端，通常与 -i 同时使用； <br>
* --name="nginx-lb": 为容器指定一个名称； <br>
* --dns 8.8.8.8: 指定容器使用的DNS服务器，默认和宿主一致； <br>
* --dns-search example.com: 指定容器DNS搜索域名，默认和宿主一致； <br>
* -h "mars": 指定容器的hostname； <br>
* -e username="ritchie": 设置环境变量； <br>
* --env-file=[]: 从指定文件读入环境变量； <br>
* --cpuset="0-2" or --cpuset="0,1,2": 绑定容器到指定CPU运行； <br>
* -m :设置容器使用内存最大值； <br>
* --net="bridge": 指定容器的网络连接类型，支持 bridge/host/none/container: 四种类型； <br>
* --link=[]: 添加链接到另一个容器； <br>
* --expose=[]: 开放一个端口或一组端口； <br>  

**实例**<br>
使用docker镜像nginx:latest以后台模式启动一个容器,并将容器命名为mynginx。 <br>
>docker run --name mynginx -d nginx:latest <br>  

使用镜像nginx:latest以后台模式启动一个容器,并将容器的80端口映射到主机随机端口。 <br>
>docker run -P -d nginx:latest <br>  

使用镜像nginx:latest以后台模式启动一个容器,将容器的80端口映射到主机的80端口,主机的目录/data映射到容器的/data。 <br>
>docker run -p 80:80 -v /data:/data -d nginx:latest <br>  

使用镜像nginx:latest以交互模式启动一个容器,在容器内执行/bin/bash命令。 <br>
>runoob@runoob:~$ docker run -it nginx:latest /bin/bash <br>
>root@b8573233d675:/# <br>
