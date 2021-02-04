## 权限配置

```
sudo chmod -R 777 ./*
sudo chown -R 1000:1000 ./*
```



## 启动组件

浏览器访问：ip+端口，如：192.168.11.111:9000

**初始密码：**

sonarqube管理员账号密码都是：admin

nexus3在容器内的 /opt/sonatype/sonatype-work/nexus3/ 目录下的 **admin.password** 文件中



## Nexus配置

maven仓库默认配置/root/.m2



## jenkin配置

1、拷贝cloudbees-folder.hpi到jenkins目录/jenkins/war/WEB-INF/detached-plugins

2、修改镜像源https://jenkins-zh.cn/tutorial/management/plugin/update-center/
      目录：/jenkins/hudson.model.UpdateCenter.xml

推荐xmission镜像	

sed -i 's#https://updates.jenkins.io/update-center.json#http://mirror.xmission.com/jenkins/updates/update-center.json#g' hudson.model.UpdateCenter.xml

3、修改镜像源

​      目录/var/jenkins_home/updates/default.json

sed -i 's#https://updates.jenkins.io/download#https://mirrors.tuna.tsinghua.edu.cn/jenkins#g' default.json && sed -i 's#http://www.google.com#https://www.baidu.com#g' default.json

4、默认密码路径/jenkins/secrets/initialAdminPasswords



## sonar配置

http://www.itmuch.com/other/sonar/