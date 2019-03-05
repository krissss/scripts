# 说明

编译->发布到docker镜像服务器（daocloud）->由镜像服务器控制发布流程

# 使用

1. 在 gitlab 该项目目录下 *Settings->CI/CD*，设置*Variables*，

- DOCKER_IMAGE：镜像名称

- DOCKER_SREVER：镜像服务器

- DOCKER_USERNAME：登录帐号

- DOCKER_PASSWORD：登录密码

2. 修改 .gitlab-ci.yml 中的部分细节，如 node 的版本等

3. 给项目打 tag 即可进行相应的发布流程

- 发布的 tag 中包含 `-test` 的，会发布到 `$DOCKER_IMAGE-test` 镜像上

- 发布的 tag 中不包含 `-test` 的，会发布到 `$DOCKER_IMAGE` 镜像上

- 发布的镜像版本号为 `$TAG`，以及会把最新发布的镜像打上 `latest`
