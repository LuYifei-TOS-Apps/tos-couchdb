# Apache CouchDB for TOS 7

此应用使用 Apache CouchDB 3.5.3 的 Docker 官方镜像，在 x86_64 和 aarch64 TNAS 上提供单节点 JSON 文档数据库。[镜像说明](https://hub.docker.com/_/couchdb)

## 连接

1. 在 TOS 中启动 Docker Engine 和 Apache CouchDB，等容器状态健康。
2. 在 TOS Docker 管理器打开 CouchDB 容器终端，执行 `cat /var/lib/tos-couchdb/.tos-admin-password`，取得首次启动生成的口令。若旧版留下的口令文件仍归 `root` 所有，请由 NAS 管理员从该挂载对应的宿主目录读取。
3. 打开 TOS 桌面入口，或在可信网络中访问 `http://<NAS-IP>:15984/_utils/`，以 `tosadmin` 登录 Fauxton。HTTP API 使用相同主机和端口。请为应用创建单独的用户并配置数据库权限。

应用会初始化单节点所需的系统库。默认连接使用 HTTP，请限制访问范围。若修改了管理员口令，后续使用新口令。

## 数据与备份

挂载至 `/var/lib/tos-couchdb` 的应用数据目录保存数据库、索引、节点配置和初始密码。可在 Docker 管理器中查看挂载来源。备份前停止应用，再拷贝整个目录，并限制副本的读取权限。[CouchDB 备份说明](https://docs.couchdb.org/en/stable/maintenance/backups.html)

安装包与校验文件随 [GitHub Release](https://github.com/LuYifei-TOS-Apps/tos-couchdb/releases) 提供。CouchDB 遵循 [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0)。

[隐私政策](PRIVACY.md)
