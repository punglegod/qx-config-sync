# Jhon 定制说明

本仓库 fork 自 [suversal/qx-config-sync](https://github.com/suversal/qx-config-sync)，`profiles/config.yaml` 已按个人需求定制：

## 定制内容

- **只保留去广告**：suversal 的 TikTok / Gemini / Binance 分流已移除（尤其 Binance 他走香港节点，与本人「交易所只走台湾」的原则冲突）；Sub-Store、PluginHub 等工具类重写已移除。
- **去广告阵容**：底包 ddgksf2013 自带（B站、开屏、彩云天气、知乎、YouTube、微博、高德、网易云、闲鱼、小红书等）+ 毒奶网页去广告 + kelee 的贴吧/菜鸟/墨迹天气/微信公众号 + blackmatrix7 补充（Advertising 综合拦截、ZhihuAds、防劫持 Hijacking、EasyPrivacy 隐私追踪拦截、BlockHttpDNS、分流与重写双份）。
- **自己的策略组**：交易所（只走台湾，默认自有 TW-GCP）、Ai（默认家宽 Home-JP）、Telegram，外加底包兼容组（苹果服务/全球加速/国际媒体等，底包分流规则要用）。自有节点靠名字识别：TW-GCP→台湾组、Home-JP→日本组、俄勒冈-free-vm→美国组。
- **底包清洗**：ddgksf2013 底包自带一条陌生人的免费公开订阅（Ruk1ng001 freeSub），已用 patches 按关键词整段删除，避免不明节点混进自动选择/手动选择组。
- **自己的分流规则**：交易所五家域名→交易所；x.ai / stripe.com / challenges.cloudflare.com→俄勒冈节点（Grok 付费链路避开慢速家宽）；Steam 登录下载直连、商店走手动选择；网易云广告域名 reject + MITM 域名（源自 ios151/NeteasemusicAd）。
- **额外加的一个功能增强**：苹果天气增强（kelee 版，解锁 Apple 天气功能、补下一小时降水、换 AQI 数据源；非去广告，应本人要求加入；MITM 域名 weatherkit.apple.com 已并入 jhon_mitm_hosts.list）。

## 安全红线（重要）

- **本仓库是公开的，严禁把任何订阅链接、节点链接、token 提交进仓库的任何文件。** `server_remote` 永远留空。
- 生成的配置文件不含订阅。在 Quantumult X 里导入生成配置会替换整个配置文件，导入后需要在 QX 里重新添加自己的订阅（只存在手机本地，不要回传到仓库）。

## 已知取舍

- **kelee 五件套改走 GitHub 镜像（2026-10-30）**：源站 kelee.one 当前不可达（多方网络均无法连接，QX 里显示「无法连接服务器」），苹果天气增强、贴吧、菜鸟、墨迹天气、微信公众号五个插件在 config.yaml 里已改为 GitHub 镜像地址（zmjde/loon-plugins 与 mihoyo-typ/KeleeOne，已逐个核对为原文件）。kelee.one 恢复后可换回官方地址。
- 网易云去广告：底包自带 ddgksf2013 版，本配置没有叠加 ios151 版的 rewrite 部分（两套同开会冲突），只并入了它的 filter 拦截和 MITM 域名。如需切换到 ios151 版，需先 patch 掉底包那条。
