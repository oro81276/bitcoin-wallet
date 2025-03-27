# 搬瓦工VPS建站指南：宝塔面板与LNMP环境一键部署教程

本文将详细介绍如何在搬瓦工VPS上快速搭建网站环境，包含宝塔面板安装和LNMP环境配置的完整流程。搬瓦工的CN2 GIA-E和香港CN2 GIA套餐因其出色的网络性能，特别适合作为建站服务器。

## 一、准备工作：连接搬瓦工VPS

在开始安装前，请确保您已经：
1. 成功购买搬瓦工VPS套餐
2. 获取了服务器IP、SSH端口和登录凭证
3. 使用SSH工具（如Termius）连接到服务器

👉 [【点击查看】2025年最新 BandwagonHost 搬瓦工优惠码及特价云服务器方案汇总](https://bit.ly/banwagon)

## 二、宝塔面板安装指南

### 不同系统的安装命令

根据您的操作系统选择对应的安装命令：

- **Ubuntu系统**：
bash
wget -O install.sh http://download.bt.cn/install/install-ubuntu_6.0.sh && sudo bash install.sh

- **CentOS系统**：
bash
yum install -y wget && wget -O install.sh http://download.bt.cn/install/install_6.0.sh && sh install.sh

- **Debian系统**：
bash
wget -O install.sh http://download.bt.cn/install/install-ubuntu_6.0.sh && bash install.sh

### 安装过程说明
1. 执行命令后，系统会提示确认安装
2. 输入`y`并按回车继续
3. 安装通常需要1-5分钟
4. 安装完成后会显示面板登录信息（地址、用户名、密码）

## 三、LNMP环境配置指南

登录宝塔面板后：

1. 首次登录需同意用户协议
2. 系统会弹出环境安装向导
3. 推荐选择LNMP组合（Linux+Nginx+MySQL+PHP）

### 版本选择建议
- Nginx：最新稳定版
- MySQL：5.7或8.0
- PHP：推荐7.4或8.0（避免使用默认的老版本）
- 安装方式：选择"极速安装"

## 四、搬瓦工套餐选择建议

| 套餐类型 | 推荐配置 | 适用场景 |
|---------|---------|---------|
| 入门级 | 洛杉矶CN2套餐 | 个人博客/小型网站 |
| **推荐** | 洛杉矶CN2 GIA-E | 企业官网/电商平台 |
| 高端型 | 香港CN2 GIA | 对延迟敏感的业务 |

安装完成后，您可以通过宝塔面板的"消息盒子"查看安装进度。整个LNMP环境的安装可能需要15-30分钟，具体时间取决于服务器配置。

现在您已经拥有了完整的网站运行环境，可以开始创建您的第一个网站了！