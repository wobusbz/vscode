#### windows
  1. 启动  NET start com.docker.services
  2. 停止  NET stop com.docker.services
  3. 重启  NET restart com.docker.services<br/>
   
#### linux:
1. 启动 systemctl  start docker
2. 停止 systemctl  stop docker  
3. 重启 systemctl  restart docker  

#### 容器操作
1. 运行容器 docker run -it --name="wuhuarou" 831691599b88
2. 停止容器  docker stop  CONTAINERID
3. 重启容器  docker stop CONTAINERID
4. 强制停止容器 docker kill CONTAINERID
5. 删除容器  docker rm CONTAINERID
6. 强制删除容器 docker rm -f CONTAINERID
7. 批量删除容器  docker rm -f $(docker ps -qa) or docker ps -qa | docker rm
8. 后台运行容器  docker run -d NAMES
9. 查看容器日志 docker logs -t -f --tail CONTAINERID (-t 是加入的时间戳 -f 跟随最新的日志打印 --tail 数字显示多少条)
10. 查看docker进程ID  docker top  CONTAINERID
11. 查看容日内部细节 docker inspect CONTAINERID
12. 进入容器  docker attach CONTAINERID or docker exec -it CONTAINERID  区别exec可以在外部执行容器的命令
13. 从容器内部拷贝文件到主机上面  docker cp CONTAINERID:/root/wuhuarou.log  c:/
14. docker ps <br/>
-a : 列出当前所有正在运行的容器+历史上运行过的<br/>
-l : 显示最近创建的容器<br/>
-n : 显示最近n个创建的容器<br/>
-q : 静默模式，只显示容器编号<br/>
--no-trunc : 不截断输出<br/>

<br/>
--name="容器名字" 类似别名<br/>
-P : 随机端口映射<br/>
-p : 指定端口映射，以下四种<br/>
ip:hostPort:containerPort<br/>
ip::containerPort<br/>
hostPort:containerPort<br/>
containerPort<br/>

15. docker commit -a="作者" -m="描述信息" CONTAINERID  tag


#### 镜像操作
1. 批量删除镜像 docker rmi $(docker images -qa) 
2. 删除镜像 docker rmi CONTAINERID
3. 查找镜像 docker serach -s 30 NAMES (-s 查找有30个S的镜像)

#### 常用快捷键
1. ctrl + c (exit) 关闭并停止容器
2. ctrl + p + q 退出并运行容器
3. 