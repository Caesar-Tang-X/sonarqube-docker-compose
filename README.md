# SonarQube Docker Compose YML File


## 简介
    docker 一键启动 SonarQube 容器的 docker-compose.yml 配置


## 镜像环境：
	postgres:9.6.23
	sonarqube:9.9.6-community


## 导入镜像：
	docker load -i 镜像包


## 启动命令：
	docker-compose up -d


## 安装及生成数据路径：
    ├── sonarqube 
        ├── images                      镜像文件文件目录
        ├── sonarqube                   容器挂载目录
            ├── db                      	数据库目录
                └── data                   		数据库数据录
            └── app                        	应用目录
                ├── data                   		应用数据目录
				├── extensions                  应用扩展目录
				└── logs                   		应用日志目录
        ├── docker-compose.yml          docker-compose.yml
        └── README.md                   README.md


## 隐私信息配置：
	1. 默认账号：admin        默认密码：admin


## 后续操作：
### 1. 启动时目录权限问题 
#### （1）启动报错，提示没有目录权限，通过以下命令查看容器启动日志
	docker logs -f sonarqube

#### （2）修改目录权限目录权限
	chmod -R 777 ./sonarqube/app


