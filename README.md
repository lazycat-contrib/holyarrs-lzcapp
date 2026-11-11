# HolyArrs 懒猫微服打包

上游：https://github.com/HolyArrs/HolyArrs （AGPL-3.0）

集影视与音乐于一体的自托管媒体中心：媒体库、求片、日历与下载管理。

## 打包说明

- 镜像：`docker.io/holyarrs/holyarrs`（官方 Docker Hub 镜像，semver tag 如 1.0.19，amd64/arm64），由 [ca-x/lazycat-github-action](https://github.com/ca-x/lazycat-github-action) 镜像模式自动同步
- Web（6262）走 upstreams
- 数据：配置/数据库在 `/lzcapp/var/config`，媒体库与下载目录在 `/lzcapp/var/media/*`、`/lzcapp/var/downloads`
- 健康检查沿用上游镜像自带 `/holyarrs -healthcheck`

## 发布

workflow 定时 + 手动触发，镜像模式同步上游 semver tag 并发布喵喵商店。
