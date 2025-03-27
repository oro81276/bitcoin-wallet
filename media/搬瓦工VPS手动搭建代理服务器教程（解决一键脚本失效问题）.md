# 搬瓦工VPS手动搭建代理服务器教程（解决一键脚本失效问题）

## 当前可选的两种网络访问方案

1. **Just My Socks服务**  
   适合仅需基础代理需求的用户，提供即用型解决方案  
   👉 [【点击查看】2025年最新 BandwagonHost 搬瓦工优惠码及特价云服务器方案汇总](https://bit.ly/banwagon)

2. **VPS自建方案**  
   推荐使用搬瓦工VPS，支持两种主流搭建方式：
   - V2ray方案（稳定性优先）
   - Shadowsocks-libev方案（秋水逸冰一键脚本）

## 准备工作
- SSH连接工具推荐：Xshell 6（可在官网下载教育版）
- 服务器系统建议：CentOS 7 with BBR
- 必备命令安装（如遇报错）：
  bash
  yum -y install wget
  

---

## 方案一：V2ray搭建教程

### 核心优势
- 当前最稳定的代理协议之一
- 支持IP被封锁后的挽救方案
- 配置简单，维护成本低

> 注意：建议在未被封禁的IP上部署，基础速度可满足日常需求

---

## 方案二：Shadowsocks-libev一键脚本

### 安装步骤
bash
wget --no-check-certificate -O shadowsocks-all.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-all.sh
chmod +x shadowsocks-all.sh
./shadowsocks-all.sh 2>&1 | tee shadowsocks-all.log

### 配置指南
1. 选择安装版本：SS-libev
2. 设置端口号（建议10000-50000区间）
3. 加密方式推荐：
   - `aes-256-gcm`（安全性最佳）
   - `chacha20-ietf-poly1305`（移动设备优化）

---

## 客户端配置

### Windows/Mac
- 支持最新版Shadowsocks客户端
- 需选择对应加密方式

### 移动设备
- **iOS**：需要外区Apple ID下载支持GCM加密的客户端
- **Android**：推荐使用Clash等现代客户端

---

## 常见问题排查

1. **连接失败**  
   检查防火墙设置：
   bash
   firewall-cmd --list-ports
   firewall-cmd --add-port=你的端口/tcp --permanent
   firewall-cmd --reload
   

2. **速度优化**  
   启用BBR加速：
   bash
   echo "net.core.default_qdisc=fq" >> /etc/sysctl.conf
   echo "net.ipv4.tcp_congestion_control=bbr" >> /etc/sysctl.conf
   sysctl -p
   

---

## 服务器选购建议

👉 [【点击查看】2025年最新 BandwagonHost 搬瓦工优惠码及特价云服务器方案汇总](https://bit.ly/banwagon)

- CN2 GIA线路优先（低延迟）
- 内存建议1GB起步
- 月流量根据实际需求选择

> 技术声明：本教程仅用于技术研究，请遵守当地法律法规。服务器到期时间为2025年12月31日，建议及时续费。