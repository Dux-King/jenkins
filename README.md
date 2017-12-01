# **jenkins:mvn_git_jdk8_docker**

## 一、基础说明

1. ### jenkins

   版本：[2.60.3]()

   工作目录：/var/jenkins_home

2. ### maven

   版本：3.3.9

   HOME路径：/usr/local/maven

   仓库路径：/var/jenkins_home/maven_repository

3. ### git

   版本：2.11.3

4. ### jdk

   版本：openjdk-1.8.0_121

   JAVA_HOME：/usr/lib/jvm/java-1.8-openjdk

5. ### docker

   docker client版本：17.09.0-ce

## 二、使用说明

通常把/var/jenkins_home挂载出来

docker挂载宿主机/var/run/doker.sock

## 三、实例

启动命令：

docker run -d -p 18587:8080 -v /root/jenkins_home:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock --name jenkins jenkins:mvn_git_jdk8_docker

## 四、问题

如果挂载目录出现权限问题使用chmod 777 /jenkins_home