# SUEP rules dat

docker-easyconnect 适用于 SUEP 的规则，仅个人使用，不保证更新与可靠性。

## download

* [suep for mihomo](./suep.yaml)
* [suepip](./geo/ip/suep.json)
* [suepsite](./geo/geosite/suep.json)

## docker-easyconnect usage

[docker-easyconnect](https://github.com/docker-easyconnect/docker-easyconnect)

---

<https://vpn.shiep.edu.cn/>

访问 <https://vpn.shiep.edu.cn/por/ec_pkg.csp?platform=linux> 查看需要安装的版本，例如 `linux_01 7.6.3.0 0 linux_01 7.6.3.0 0 linux_01 7.6.3.0 0 linux_01 7.6.3.0 0` 表示版本为 `7.6.3`

纯命令行版 EasyConnect（amd64 架构）

```sh
docker run --name easyconnect --device /dev/net/tun --cap-add NET_ADMIN -ti \
-p 127.0.0.1:10800:1080 \
-p 127.0.0.1:18888:8888 \
-e EC_VER=7.6.7 \
-e CLI_OPTS="-d 210.35.90.35 -u 你的学号 -p 你的密码" \
hagb/docker-easyconnect:cli
```

访问 <https://vpn.shiep.edu.cn/por/ec_pkg.csp?platform=linux> 查看需要安装的版本，例如 `linux_01 7.6.3.0 0 linux_01 7.6.3.0 0 linux_01 7.6.3.0 0 linux_01 7.6.3.0 0` 表示版本为 `7.6.3`

运行图形界面版 EasyConnect（x86、amd64、arm64、mips64el 架构）

```sh
docker run --rm --device /dev/net/tun --cap-add NET_ADMIN -ti \
-e PASSWORD=114514 \
-e URLWIN=1 \
-e DISABLE_PKG_VERSION_XML=1 \
-v $HOME/.ecdata:/root \
-p 127.0.0.1:5901:5901 \
-p 127.0.0.1:10800:1080 \
-p 127.0.0.1:18888:8888 \
-e CLIP_TEXT=https://vpn.shiep.edu.cn/ \
hagb/docker-easyconnect:7.6.3
```

使用 vnc viewer 连接，连接地址为 `127.0.0.1:5901`，连接密码为 `114514`

随后在 vnc viewer 查看 EasyConnect，输入学号密码即可登录。
