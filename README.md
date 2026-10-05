# s5-serv00

serv00 用的 SOCKS5 管理脚本。基于 [ryty1/s5](https://github.com/ryty1/s5) 的 `os.sh` 修改。

## 相比原版新增

- **6) 重启服务**：杀掉旧进程（明文进程名 + 伪装进程名都匹配），重新拉起并确认
- **7) 保活管理**：一键开启/关闭；开启后写 cron，每 5 分钟检查一次服务进程，掉了自动拉起
- 卸载时自动清理保活的 cron

## 使用

```sh
curl -fsSLO https://raw.githubusercontent.com/saodisengyyds/s5-serv00/main/os.sh
bash os.sh
```

## 说明

- 目标环境：serv00（FreeBSD），探针脚本为 POSIX sh，cron 下 python 路径写死
- 安装时会从上游下载 `get.py` / `s5.enc`，请自行确认来源可信
