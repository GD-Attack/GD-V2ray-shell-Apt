# GD-V2ray-shell-Apt
GD-V2ray-shell-Apt，通过shell脚本部署VPN节点
使用时，需要将三个脚本移动到/root文件夹下，将v2ray.sh赋予x可执行权限，然后执行v2ray.sh文件即可部署


# Xray & Clash 一键自动化部署脚本

这是一个用于在 Linux (CentOS / Rocky Linux / RHEL 系列) 上一键部署 Xray (VLESS-REALITY / VMess) 服务并自动生成 Clash 订阅配置文件的 Bash 脚本套件。

## 🌟 项目特点

- **自动安装依赖**：自动检测并安装 HTTPD、Firewalld、Curl 等必要的工具。
- **防火墙自动放行**：自动配置 80 (HTTP) 和 443 (HTTPS) 端口。
- **自动密钥生成**：自动生成 UUID、Public Key / Short ID 或必要参数。
- **Clash 订阅生成**：将节点配置自动输出为 `clash.yaml` 并由 Web 服务托管，方便直接导入客户端。

---

## 📁 文件结构说明

下载或克隆本仓库后，请确保以下三个文件处于同一目录下（通常为 `/root`）：

- `v2ray.sh` ：**主执行脚本**，负责环境检查、安装 Xray、运行子脚本及检测服务状态。
- `v2ray_xray.sh` ：**Xray 服务端配置生成脚本**，生成 `/usr/local/etc/xray/config.json`。
- `v2ray_clash.sh` ：**Clash 客户端配置生成脚本**，生成 `/var/www/html/clash.yaml`。

---

## 🚀 快速使用指南

### 使用说明

```bash
cd /root
# 确保 v2ray.sh, v2ray_xray.sh, v2ray_clash.sh 三个脚本都在该目录下


chmod +x v2ray.sh v2ray_xray.sh v2ray_clash.sh
./v2ray.sh

==========================================
Clash 订阅地址: http://<你的服务器IP>/clash.yaml
==========================================

