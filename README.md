<div align="center">

# Awesome TVBox

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](LICENSE)
[![Last checked](https://img.shields.io/badge/last%20checked-2026--11--12-blue.svg)](#来源与致谢)

TVBox / 影视仓 / FongMi 影视 生态资源合集：客户端软件 · 配置接口 · 直播源 · 开发文档 · 实用工具

**简体中文** | [English](README.en.md)

</div>

> [!WARNING]
> **免责声明**：本仓库只整理互联网上公开可访问的链接，**不存储、不分发**任何影视内容、安装包或接口文件。TVBox 类软件本身是不含片源的“空壳”播放器，接口中的内容由第三方提供，其合法性与版权与本仓库无关。请遵守所在地法律法规，支持正版。本仓库内容仅供学习与技术研究，如有侵权请[提交 Issue](https://github.com/jiji262/awesome-tvbox/issues) 联系删除。

## 目录

- [什么是 TVBox](#什么是-tvbox)
- [快速上手](#快速上手)
- [客户端软件](#客户端软件)
  - [开源客户端](#开源客户端)
  - [桌面与跨平台](#桌面与跨平台)
  - [直播软件](#直播软件)
  - [盒子软件合集](#盒子软件合集)
- [配置接口](#配置接口)
  - [优选接口](#优选接口)
  - [备用接口](#备用接口)
  - [GitHub 接口仓库](#github-接口仓库)
  - [资源与导航站点](#资源与导航站点)
- [直播源 IPTV](#直播源-iptv)
  - [直播源仓库](#直播源仓库)
  - [EPG 节目单与台标](#epg-节目单与台标)
- [开发与文档](#开发与文档)
  - [官方文档](#官方文档)
  - [入门教程](#入门教程)
  - [配置文件格式速查](#配置文件格式速查)
  - [爬虫与源开发](#爬虫与源开发)
- [实用工具](#实用工具)
- [社区与频道](#社区与频道)
- [相关 Awesome 列表](#相关-awesome-列表)
- [来源与致谢](#来源与致谢)
- [参与贡献](#参与贡献)
- [许可协议](#许可协议)

## 什么是 TVBox

TVBox 是一款开源的 Android 电视盒子影视软件，最早由 `CatVodTVOfficial/TVBoxOSC` 开源（原仓库现已删除），其爬虫接口沿用猫影视（CatVod）的 Spider 规范。软件本身不含任何片源：用户填入一个**配置接口**（JSON 地址）后，软件按接口中的**站点**（苹果 CMS 采集站或爬虫 Spider）获取点播内容，按**直播源**（M3U / TXT）播放电视直播。

围绕它形成了庞大的生态：

- **客户端**：TVBox 各分支（takagen99、q215613905 等）、FongMi 影视、影视仓、WebHomeTV，以及大量二次打包的“空壳”软件；
- **配置接口**：饭太硬、肥猫、王二小、菜妮丝等社区维护的接口，以“单仓 / 多仓”形式分享；
- **直播源**：IPTV 直播源仓库、EPG 节目单与台标；
- **开发**：CatVod Spider（Java / JS / Python）、drpy 规则引擎、T4 服务端源等。

## 快速上手

1. **安装客户端**：在[客户端软件](#客户端软件)中挑选一个，电视 / 盒子选 TV 版，手机选手机版。电视安装 APK 可用 U 盘、[当贝市场](https://www.dangbei.com/apps/) / [沙发管家](https://www.shafa.com/) 等电视助手类应用，或在局域网内用 ADB：`adb connect 电视IP:5555`，再 `adb install 文件名.apk`。各品牌设备的安装方法见[入门教程](#入门教程)。
2. **填写配置接口**：打开软件，进入「设置 → 配置地址」，粘贴[配置接口](#配置接口)中的地址并确认，软件会自动加载站点。多仓接口（JSON 中含 `urls`）会列出多条“线路 / 仓库”供切换。
3. **切换站点**：首页可切换“站点 / 数据源”，播放失败时换个站点或线路即可。
4. **看直播**：在「直播地址」中填写 M3U / TXT 直播源（见[直播源 IPTV](#直播源-iptv)），或直接使用带 `lives` 的配置接口。

> [!TIP]
> - 中文域名接口在部分设备上无法输入或解析，可改用 Punycode 形式，例如 `饭太硬.net` → `xn--sss604efuw.net`、`肥猫.net` → `xn--z7x900a.net`，表格“说明”栏已标注对应的中文域名。
> - “图片封装”指配置内容被藏在图片文件里，“加密”指配置内容经过编码加密，主流新版客户端都能自动识别；老版本加载失败时请升级客户端。
> - 接口失效很常见，建议多备几条。下表状态为 2026-11-12 的抽检快照，仅代表当时能否访问。

## 客户端软件

### 开源客户端

| 项目 | 说明 | ⭐ | 最近更新 |
|---|---|---|---|
| [j4Uq/TVBoxOSC](https://github.com/j4Uq/TVBoxOSC) | TVBox 自动构建发布（原 o0HalfLife0o/TVBoxOSC），每日编译 takagen99/Box 与 q215613905/TVBoxOS 等分支 APK · [Releases](https://github.com/j4Uq/TVBoxOSC/releases) · [Telegram](https://t.me/TVBoxOSC) | 18.2k | 2026-11 |
| [FongMi/TV](https://github.com/FongMi/TV) | 影視TV（FongMi 影视），Android TV、手机、平板通用：点播、直播、弹幕、DLNA 投放、网页遥控，支持 Java / Python / QuickJS 爬虫 · [使用指南](https://fongmi.github.io/TV/) · [安装包](https://github.com/FongMi/Release/releases) · [Telegram](https://t.me/fongmi_official) | 10.5k | 2026-11 |
| [liu673cn/bug](https://github.com/liu673cn/bug) | TVBox 开源版空壳（已停更，存档参考） | 10.3k | 2023-12 |
| [takagen99/Box](https://github.com/takagen99/Box) | TVBox 的 takagen99 分支 | 3.1k | 2026-02 |
| [q215613905/TVBoxOS](https://github.com/q215613905/TVBoxOS) | TVBox 二开分支，README 附完整 JSON 配置示例 | 3k | 2026-11 |
| [webhtv/webhtv](https://github.com/webhtv/webhtv) | WebHomeTV，基于 FongMi 二开，WebHome 自定义首页、网盘链接检测 · [Telegram](https://t.me/webhtv) | 1.9k | 2026-11 |
| [XiaochangXu/AVBox](https://github.com/XiaochangXu/AVBox) | Material Design 3 全新设计的多平台 TVBox | 675 | 2026-11 |
| [motao123/webtv](https://github.com/motao123/webtv) | 基于 FongMi / CatVod 二开的 Android TV 影音聚合客户端 | 201 | 2026-11 |
| [xixu-me/fongmi-tv-actions-builder](https://github.com/xixu-me/fongmi-tv-actions-builder) | 用 GitHub Actions 自动编译并发布签名版 FongMi TV APK | 53 | 2026-10 |
| [zongchenghuan0318/TVBox-fashion-UI](https://github.com/zongchenghuan0318/TVBox-fashion-UI) | Z影视，基于 TVBoxOSC 二开的多源聚合客户端 | 44 | 2026-11 |
| [dhicoc/FusionTV-KitKat](https://github.com/dhicoc/FusionTV-KitKat) | 基于 OK影视 的 Android 4.4 (ARM32) 老电视优化版 | 11 | 2026-10 |

> 原版 TVBox 仓库 `CatVodTVOfficial/TVBoxOSC` 已删除，各分支的自动构建版可在 [j4Uq/TVBoxOSC Releases](https://github.com/j4Uq/TVBoxOSC/releases) 获取。

### 桌面与跨平台

| 项目 | 说明 | ⭐ | 最近更新 |
|---|---|---|---|
| [Hiram-Wong/zyfun](https://github.com/Hiram-Wong/zyfun) | zyfun（原 ZyPlayer），跨平台桌面视频播放器，支持 TVBox 类源 | 9.1k | 2026-06 |
| [kknifer7/FreeBox](https://github.com/kknifer7/FreeBox) | TVBox 电脑版 / 姊妹软件，扩展 TVBox 生态到桌面 | 2.1k | 2026-07 |
| [Greatwallcorner/TV-Multiplatform](https://github.com/Greatwallcorner/TV-Multiplatform) | 基于 FongMi/TV 的桌面版实现 | 718 | 2026-01 |
| [hgtuj5688/tvbox-desktop](https://github.com/hgtuj5688/tvbox-desktop) | TVBox Desktop：极简 Windows 影视聚合客户端，可直接导入 TVBox 配置订阅，支持 M3U / TXT 直播 | 359 | 2026-09 |
| [yagami-hue/Win-box](https://github.com/yagami-hue/Win-box) | Windows 版 TVBox | 350 | 2026-11 |
| [yuluoos/TVBox-tvs](https://github.com/yuluoos/TVBox-tvs) | TVS：Flutter 空壳播放器（Android TV / iOS / iPadOS / macOS），仅支持羊壳（PeekPro）订阅与 M3U / TXT / JSON 直播源，不保证兼容 TVBox 配置 · [下载页](https://yuluoos.github.io/TVBox-tvs/) | 240 | 2026-11 |
| [sky22333/sky-tv](https://github.com/sky22333/sky-tv) | 跨平台视频播放器，可导入自定义影视源与 IPTV 直播源 | 139 | 2026-10 |
| [yaolin-dev/OKVideoMac](https://github.com/yaolin-dev/OKVideoMac) | 原生 macOS（Apple Silicon）IPTV / 点播播放器 | 124 | 2026-11 |
| [cwe88108/free-new-desk-public](https://github.com/cwe88108/free-new-desk-public) | Windows 11 x64 的 TVBox / FongMi 风格桌面播放器 | 121 | 2026-10 |
| [zhujinrun/FongMi-Player](https://github.com/zhujinrun/FongMi-Player) | 基于影视 APP 扩展的跨平台桌面播放器，解析主流 TVBox 源 | 32 | 2026-11 |
| [LanLanff/FlyTV](https://github.com/LanLanff/FlyTV) | TVBox 电脑版（Windows），免安装绿色包，网盘播放 / 弹幕 / 历史同步 | 28 | 2026-11 |
| [jianbinzhang1987/OKPlayer](https://github.com/jianbinzhang1987/OKPlayer) | 兼容 FongMi / TVBox 配置格式的跨平台桌面播放器 | 17 | 2026-11 |
| [tengdechun/tvbox-desktop](https://github.com/tengdechun/tvbox-desktop) | TVBox / CatVod 兼容的 Windows 桌面客户端 | 12 | 2026-08 |
| [shareu007/tvbox-Swift-macOS](https://github.com/shareu007/tvbox-Swift-macOS) | 原生 SwiftUI 的 TVBox 客户端（macOS / iOS） | 9 | 2026-10 |
| [wj5403293/KOTV](https://github.com/wj5403293/KOTV) | Flutter / Go 跨端影视聚合客户端，兼容 CatVod 配置生态 | 6 | 2026-08 |

### 直播软件

| 项目 | 说明 | ⭐ | 最近更新 |
|---|---|---|---|
| [lizongying/my-tv](https://github.com/lizongying/my-tv) | 我的电视，安装即用的电视直播软件（2024 年后停更） | 32k | 2024-06 |
| [lizongying/my-tv-0](https://github.com/lizongying/my-tv-0) | 我的電視·〇，可自定义视频源的直播软件 | 4.7k | 2025-05 |
| [mytv-android/mytv-android](https://github.com/mytv-android/mytv-android) | 天光云影，Material 3 Expressive 风格的 Android / Android TV 直播播放器 · [使用文档](https://mytv-android.github.io/mytv-doc/) | 3.1k | 2026-11 |
| [Kimentanm/aptv](https://github.com/Kimentanm/aptv) | APTV：Apple 全平台（iOS / iPadOS / tvOS / macOS / watchOS）直播播放器，支持 M3U、回看与节目单 · [App Store](https://apps.apple.com/cn/app/aptv/id1630403500) | 2.9k | 2026-11 |
| [yaoxieyoulei/mytv-android](https://github.com/yaoxieyoulei/mytv-android) | 天光云影原项目（已归档） | 1.9k | 2025-09 |
| [HTWMedia/HTV](https://github.com/HTWMedia/HTV) | 免费无广告的电视直播 App，手机与电视盒子通用 | 832 | 2026-11 |

### 盒子软件合集

以下 31 款软件的版本与更新日期截至 2026-11-12，下载链接为夸克网盘 / 光鸭网盘分享。其中 3 款“去广告 / 高级版”修改版不提供下载链接。这些软件多为闭源的第三方打包版本，安装前请自行甄别。

| 软件 | 版本 | 平台 | 简介 | 更新 | 下载 |
|---|---|---|---|---|---|
| 橘汁 | 3.0.7.1 (去广告) | Android | 安卓、电视版影视软件，高清路线 | 2026-11-11 | 修改版，未收录 |
| 免费电视 | 261012 | Android | 电视直播与频道观看 | 2026-11-04 | [夸克](https://pan.quark.cn/s/39c87e087ff0) · [光鸭](https://www.guangyapan.com/s/1965091076424675358_aeoR4oULFG4aU0pK) |
| 归零box | 1.5.13 | TV | TVBox影视点播与直播工具 | 2026-11-04 | [夸克](https://pan.quark.cn/s/62834910c0f9) · [光鸭](https://www.guangyapan.com/s/1965091202564161578_aeoR4oULFG4aU0pK) |
| 高清直播 | 1.1.2 | TV | 高清电视直播频道播放软件 | 2026-11-04 | [夸克](https://pan.quark.cn/s/3bc9e450c24c) · [光鸭](https://www.guangyapan.com/s/1965091225150500915_aeoR4oULFG4aU0pK) |
| 电视家 | 9.9.9 | TV | 免费观看央视卫视电视直播 | 2026-11-04 | [夸克](https://pan.quark.cn/s/1337ca2f056e) · [光鸭](https://www.guangyapan.com/s/1965091293429518386_aeoR4oULFG4aU0pK) |
| 影视仓 | 6.2.9 | TV | 基于TvBox二开，空壳 | 2026-11-04 | [夸克](https://pan.quark.cn/s/154038a9cbaa) · [光鸭](https://www.guangyapan.com/s/1953049516944642140_aeoR4oULFG4aU0pK) |
| 默影视 | 5.6.0 | Android / TV | 点播、直播、空壳软件，适配TvBox接口 | 2026-11-04 | [夸克](https://pan.quark.cn/s/5b20c49599e3) · [光鸭](https://www.guangyapan.com/s/1941113271887003656_aeoR4oULFG4aU0pK) |
| 超级直播 | 3.2.0 | Android | 电视直播，简洁无广告 | 2026-10-28 | [夸克](https://pan.quark.cn/s/f974d506bd84) · [光鸭](https://www.guangyapan.com/s/1945878610387382353_aeoR4oULFG4aU0pK) |
| NewBox | 2.1.1 | TV | 点播、直播、空壳软件，适配TvBox接口 | 2026-10-27 | [夸克](https://pan.quark.cn/s/4c875099c325) · [光鸭](https://www.guangyapan.com/s/1936828671156740158_aeoR4oULFG4aU0pK) |
| FongMi影视 | 5.8.4 | TV | 基于猫影视开源项目开发 | 2026-10-27 | [夸克](https://pan.quark.cn/s/52095963630b) · [光鸭](https://www.guangyapan.com/s/1941081829538717706_aeoR4oULFG4aU0pK) |
| 天下直播 | 3.1.1 | TV | 电视直播软件 | 2026-10-07 | [夸克](https://pan.quark.cn/s/90ba5c0c93b3) · [光鸭](https://www.guangyapan.com/s/1954901836208779270_aeoR4oULFG4aU0pK) |
| 蝴蝶影院 | 5.0.0 | TV | 影视剧资源丰富的盒子软件 | 2026-10-06 | [夸克](https://pan.quark.cn/s/3cf740bc3854) · [光鸭](https://www.guangyapan.com/s/1954402126582747218_aeoR4oULFG4aU0pK) |
| WebHomeTV | 5.6.0 | TV | 点播、直播、空壳软件，适配TvBox接口 | 2026-10-02 | [夸克](https://pan.quark.cn/s/dafac8daa686) · [光鸭](https://www.guangyapan.com/s/1941882633636270121_aeoR4oULFG4aU0pK) |
| 星河TV | 2.0.355 | Android | 多频道播放器，播放无延迟 | 2026-10-02 | [夸克](https://pan.quark.cn/s/aa6c08a75b44) · [光鸭](https://www.guangyapan.com/s/1944067664597577758_aeoR4oULFG4aU0pK) |
| 电视影院TV | 9.1 | TV | 内置接口，随意注册即可 | 2026-09-21 | [夸克](https://pan.quark.cn/s/801c3bd67ac6) · [光鸭](https://www.guangyapan.com/s/1949118544087859211_aeoR4oULFG4aU0pK) |
| 星火电视 | 1.0.53.1 | TV | 电影，记录中国，食谱，春晚，演唱会，歌曲 | 2026-09-21 | [夸克](https://pan.quark.cn/s/8c87fd7bbbc6) · [光鸭](https://www.guangyapan.com/s/1949118566921633837_aeoR4oULFG4aU0pK) |
| 星落 | 6.0.0.6 | TV | 适配TvBox接口，手机/电视版 | 2026-09-20 | [夸克](https://pan.quark.cn/s/1e4ce4ce4c00) · [光鸭](https://www.guangyapan.com/s/1937165723928780867_aeoR4oULFG4aU0pK) |
| 青龙TV | 1.0.0 | TV | 无广告电视直播软件 | 2026-09-17 | [夸克](https://pan.quark.cn/s/7f5713f40bd7) · [光鸭](https://www.guangyapan.com/s/1947673428349116436_aeoR4oULFG4aU0pK) |
| TVBox | 20260914 | TV | TvBoxQ版原版软件，空壳版 | 2026-09-15 | [夸克](https://pan.quark.cn/s/6f98da0cfe6a) · [光鸭](https://www.guangyapan.com/s/1941082816995323952_aeoR4oULFG4aU0pK) |
| uzn | 1.1.8 | Android / Windows / iOS / macOS | 点播、直播、空壳软件，下载链接附接口 | 2026-09-13 | [夸克](https://pan.quark.cn/s/66f5d84631f6) · [光鸭](https://www.guangyapan.com/s/1945915658997579844_aeoR4oULFG4aU0pK) |
| 网视TV | 1.0.0 | TV | — | 2026-09-12 | [夸克](https://pan.quark.cn/s/a96426a0ebf8) · [光鸭](https://www.guangyapan.com/s/1945868041672437815_aeoR4oULFG4aU0pK) |
| 星视TV | 1.3.4 | TV | — | 2026-09-12 | [夸克](https://pan.quark.cn/s/3fae3afb0440) · [光鸭](https://www.guangyapan.com/s/1939014577938800708_aeoR4oULFG4aU0pK) |
| PeekPro | 1.5.7 | Android / Windows / iOS | — | 2026-09-06 | [夸克](https://pan.quark.cn/s/2ab3e47ab079) · [光鸭](https://www.guangyapan.com/s/1941112278587773009_aeoR4oULFG4aU0pK) |
| 星微短剧 | 828 | Android / TV | — | 2026-08-31 | [夸克](https://pan.quark.cn/s/efee3dcfb6eb) · [光鸭](https://www.guangyapan.com/s/1941542559530754095_aeoR4oULFG4aU0pK) |
| 智哥影视 | 2.8.9 | TV | — | 2026-08-30 | [夸克](https://pan.quark.cn/s/a2a2b4406466) · [光鸭](https://www.guangyapan.com/s/1941113547586965521_aeoR4oULFG4aU0pK) |
| 魄狼TV | 1.0.7 | TV | — | 2026-08-30 | [夸克](https://pan.quark.cn/s/7e428118e868) · [光鸭](https://www.guangyapan.com/s/1941113371342340190_aeoR4oULFG4aU0pK) |
| 畅映TV | 1.9.0 (去广告) | Android | — | 2026-08-22 | 修改版，未收录 |
| 电影侠 | 3.5.0 | TV | — | 2026-08-19 | [夸克](https://pan.quark.cn/s/8ee87d237d6c) · [光鸭](https://www.guangyapan.com/s/1937161724152426532_aeoR4oULFG4aU0pK) |
| GD影视 | 5.4.1.13 | TV | — | 2026-08-18 | [夸克](https://pan.quark.cn/s/629b7a9993fb) · [光鸭](https://www.guangyapan.com/s/1936828432714727505_aeoR4oULFG4aU0pK) |
| 宸龙影视 | 5.6.0 | Android / TV | — | 2026-08-17 | [夸克](https://pan.quark.cn/s/fb75db7f0514) · [光鸭](https://www.guangyapan.com/s/1936440748947198017_aeoR4oULFG4aU0pK) |
| 追光影院 | 9.94 (高级版) | TV | — | 2026-08-16 | 修改版，未收录 |

## 配置接口

将下表中的“接口地址”填入客户端的「配置地址」即可使用。状态说明：✅ 可访问（含 JSON、图片封装、加密三种形式）；⚠️ 连接受阻（HTTPS 握手失败，可能仅在特定网络下可用）；❌ 失效（域名无法解析或返回 404 / 403）。

### 优选接口

| 名称 | 说明 | 接口地址 | 状态 |
|---|---|---|---|
| 王二小 | 混合线路，以网盘(4K)为主，适合网盘VIP用户 | `https://9280.kstore.vip/newwex.json` | ✅ |
| 菜妮丝 | 常规线路，推荐瓜子、金牌等线路（即 `tv.菜妮丝.top`） | `https://tv.xn--yhqu5zs87a.top` | ✅ |
| 饭太硬 | 混合线路，推荐荐片等线路 | `http://www.饭太硬.net/tv` | ✅ 图片封装 |
| 肥猫 | 混合线路，推荐肥猫、瓜子、金牌等线路 | `http://肥猫.net/` | ✅ 加密 |
| 少儿频道 | 常规线路，启蒙、少儿、小/初/高 | `https://jihulab.com/ymz1231/xymz/-/raw/main/ymshaoer` | ✅ 图片封装 |
| 俊哥 | 常规线路 | `http://home.jundie.top:81/top98.json` | ✅ |
| 小盒子 | 常规线路 | `http://xhztv.top/xhz` | ✅ |
| 4k云盘接口 | 混合线路，可用性较差 | `https://9xi4o.tk/0725.json` | ❌ 域名失效 |
| 无意云 | 混合线路，若不用网盘的话可以选排序靠后的线路，画质较高 | `https://ym.wya6.cn/` | ❌ 域名失效 |
| 欧歌接口 | 常规影视线路（即 `sd欧歌ds.v.nxog.top`） | `https://xn--sdds-rp5imh.v.nxog.top/apitv.php?id=3` | ⚠️ 连接受阻 |

### 备用接口

| 名称 | 说明 | 接口地址 | 状态 |
|---|---|---|---|
| 小盒子4K | 4K高清线路 | `http://xhztv.top/4k.json` | ✅ |
| 少儿频道 | 常规线路，启蒙、少儿、小/初/高 | `https://jihulab.com/ymz1231/xymz/-/raw/main/ymshaoer` | ✅ 图片封装 |
| 二月红接口 | 综合影视源 | `https://700sjro44343.vicp.fun/eggp/0211/tv.json` | ✅ |
| 俊哥接口 | 常规线路 | `http://home.jundie.top:81/top98.json` | ✅ |
| 欧歌免费 | 欧歌免费公用线路 | `https://tv.nxog.top/m/111.php?ou=公众号欧歌app&mz=index&jar=index&123&b=tv` | ⚠️ 连接受阻 |
| 王二小接口 | 王二小备用线路（即 `tvbox.王二小放牛娃.top`） | `http://tvbox.xn--4kq62z5rby2qupq9ub.top/` | ✅ |
| 王二小放牛娃 | 王二小网盘备用源 | `http://tv.999888987.xyz` | ✅ |
| 饭太硬 | 混合线路，推荐荐片等线路 | `https://qist.wyfc.qzz.io/fty.json` | ✅ |
| 潇洒 | 综合高清线路 | `https://qist.wyfc.qzz.io/xiaosa/api.json` | ✅ |
| 牛二 | 网盘4K混合线路 | `https://9280.kstore.space/newwex.json` | ✅ |
| uuccc | 通用影视线路（即 `影视仓.com`） | `http://xn--5mqx81b535a.com/` | ✅ |
| fmys | 综合聚合线路 | `http://fmys.top/fmys.json` | ❌ 404 |
| 饭太硬备用 | 饭太硬备用访问地址 | `https://fty.888484.xyz/tv` | ✅ 图片封装 |
| 新接口 | 全新综合聚合源 | `https://www.iyouhun.com/tv/wex` | ✅ |
| ok线路1 | 稳定通用影视源 | `https://raw.liucn.cc/box/m.json` | ✅ |
| 荐片 | 荐片高清专用线路 | `https://tv.203511.xyz/0821.json` | ✅ |
| my interface | 自建本地接口源 | `http://124.223.214.31:8/api.json` | ✅ |
| 1号VIP源 | VIP付费影视线路 | `https://700sjro44343.vicp.fun/vip/vip/tv.json` | ✅ |
| 软件内置源 | 本地端口服务接口 | `http://47.96.82.41:5188/api.json` | ✅ |
| ok线路2 | Gist托管备用源 | `https://gist.githubusercontent.com/ph7368/20ee6c7b64d77d82f8f4162cdd04ad61/raw/gistfile1.txt` | ✅ |
| 11号托管源 | Github静态加速源 | `https://cdn.jsdelivr.net/gh/liu673cn/box@main/m.json` | ✅ |
| 摸鱼儿 | 鱼影视专用线路 | `https://6800.kstore.vip/fish.json` | ✅ |
| sss公用源 | 长期稳定通用线路（即 `饭太硬.net`） | `http://www.xn--sss604efuw.net/tv` | ✅ 图片封装 |
| 牛儿 | 牛二同站备用wex源 | `https://9280.kstore.space/wex.json` | ✅ |
| 拾光 | SVIP高清影视托管源 | `https://gh-proxy.com/https://raw.githubusercontent.com/xmbjm/svip/refs/heads/main/svip.json` | ✅ |
| 神秘大佬 | Github加速聚合综合源 | `https://g.33445500.xyz/https://raw.githubusercontent.com/qist/tvbox/refs/heads/master/jsm.json` | ✅ |
| 潇洒Github备用 | 潇洒线路镜像加速地址 | `https://g.33445500.xyz/https://raw.githubusercontent.com/qist/tvbox/refs/heads/master/xiaosa/api.json` | ✅ |
| 小苹果线路 | Bitbucket托管苹果影视源 | `https://bitbucket.org/xduo/duoapi/raw/master/xpg.json` | ❌ 404 |
| 66号GitCode源 | 国内Gitee类静态影视接口 | `https://raw.gitcode.com/jvftibcs-jbduyh/021/raw/main/18.json` | ❌ 403 |
| 金鹰 | 金鹰影视专用聚合线路 | `http://550.3vcn.work/wdjyys.json` | ✅ |

### GitHub 接口仓库

社区维护的配置仓库，通常在 README 中给出单仓 / 多仓地址，部分使用 GitHub Actions 自动更新。

| 项目 | 说明 | ⭐ | 最近更新 |
|---|---|---|---|
| [qist/tvbox](https://github.com/qist/tvbox) | OK影视、TVBox 配置文件（多仓 / 单仓 / jar 合集） | 12.8k | 2026-11 |
| [gaotianliuyun/gao](https://github.com/gaotianliuyun/gao) | FongMi 影视与 TVBox 配置文件（2024 年后停更） | 8.2k | 2024-11 |
| [2hacc/TVBox](https://github.com/2hacc/TVBox) | TVBox 网络接口（2024 年后停更） | 5.9k | 2024-12 |
| [noimank/tvbox](https://github.com/noimank/tvbox) | 自用 TVBox 源、影视仓多仓源与相关资源记录 | 3.7k | 2026-08 |
| [xianyuyimu/TVBOX-](https://github.com/xianyuyimu/TVBOX-) | 一木 TVBox 自用仓库 | 3.1k | 2026-09 |
| [Zhou-Li-Bin/Tvbox-QingNing](https://github.com/Zhou-Li-Bin/Tvbox-QingNing) | 青柠：TVBox / 影视仓接口与直播源（单仓 / 多仓） · [官网](https://132130.com) | 2.1k | 2026-11 |
| [Dong-learn9/TVBox-zyjk](https://github.com/Dong-learn9/TVBox-zyjk) | TVBox 自用接口 | 1.6k | 2025-01 |
| [jinenge/tvbox](https://github.com/jinenge/tvbox) | TVBox / 影视仓内置源，持续更新 | 1.2k | 2026-06 |
| [xiongjian83/TvBox](https://github.com/xiongjian83/TvBox) | TVBox 接口 | 702 | 2026-11 |
| [cluntop/tvbox](https://github.com/cluntop/tvbox) | TVBox 接口 / OK影视 | 675 | 2026-11 |
| [yangxiaoge/tvbox_cust](https://github.com/yangxiaoge/tvbox_cust) | TVBox 自定义配置（作者声明仅自用） | 634 | 2026-11 |
| [wuxierj/TVBox](https://github.com/wuxierj/TVBox) | TVBox、影视仓接口大全 | 418 | 2026-05 |
| [Lightconer/tvbox-ysc-config](https://github.com/Lightconer/tvbox-ysc-config) | 影视仓 / TVBox 配置聚合，GitHub Actions 每日自动更新（肥猫 / 饭太硬 / 王二小等） | 397 | 2026-11 |
| [kimwang1978/tvbox](https://github.com/kimwang1978/tvbox) | 自用影视仓 / TVBox 配置 | 396 | 2025-11 |
| [CandyMuj/ResourceInterface](https://github.com/CandyMuj/ResourceInterface) | 各类资源软件接口合集（TVBox、阅读等） | 304 | 2026-11 |
| [ne7359/tvurl](https://github.com/ne7359/tvurl) | OK影视、TVBox 配置文件 | 301 | 2026-11 |
| [yoursmile66/TVBox](https://github.com/yoursmile66/TVBox) | TVBox 接口（json + jar + 直播源） | 258 | 2026-11 |
| [niubihu1/tvbox](https://github.com/niubihu1/tvbox) | 牛虎 TVBox 聚合接口（单仓 / 多仓） | 225 | 2026-11 |
| [mrgaoshuiquan/tvbox-config](https://github.com/mrgaoshuiquan/tvbox-config) | 基于"饭太硬"修改的自用配置 | 155 | 2026-08 |
| [chendi0207/my-TVBOX](https://github.com/chendi0207/my-TVBOX) | 收集自网络的 TVBox 接口 | 150 | 2026-11 |
| [TVboxorg/TVbox](https://github.com/TVboxorg/TVbox) | TVBox 接口汇总与可用性探测 · [官网](https://www.tvbox.org/) | 26 | 2026-11 |
| [jiusanzhou/tvbox](https://github.com/jiusanzhou/tvbox) | 多站点配置合并为一个订阅链接 | 22 | 2026-11 |
| [shengshimeiyan/fty44safe](https://github.com/shengshimeiyan/fty44safe) | Android 4.4 老盒子专用接口（无 spider jar，纯 type:1） | 12 | 2026-09 |
| [dxyc0922/Tvbox4.x_api](https://github.com/dxyc0922/Tvbox4.x_api) | 适配安卓 4.x 老设备的 TVBox 接口 | 8 | 2026-11 |

### 资源与导航站点

常用资源站点：

| 站点 | 说明 |
|---|---|
| [口袋猫](https://www.kdmao.com/category/tv) | 盒子软件长期更新 |
| [小盒子工具箱](https://www.xhztv.pro/) | 软件、接口收集更新及制作 |
| [江江TVBox](https://tv.xn--9swa.com/) | TvBox、IPTV接口收集（`tv.江江.com`） |
| [硬核指南TvBox](https://yinghezhinan.com/tvbox-jsonlist/) | TvBox接口收集 |

其他接口导航与聚合站：

- [聚玩盒子 · 数据源](https://www.juwanhezi.com/jsonlist)：单仓 / 多仓 / 本地包接口列表，逐条显示可用性探测结果；同站另有[直播源列表](https://www.juwanhezi.com/live)。
- [硬核指南 · 影视仓配置接口](https://yinghezhinan.com/yingshicang-jiekou/)：与上表“硬核指南TvBox”同站，按单仓 / 多仓整理并附说明。
- [源仓库（yckceo）](https://www.yckceo.com/index/applist/tvbox.html)：TVBox 客户端介绍与多家接口资源汇总。
- [资源收藏夹 · TV盒子与直播](https://zyscj.com/zy/video/tv.html)：人工整理的盒子软件、接口与直播源链接。

## 直播源 IPTV

直播源一般是 M3U / TXT 文件，可直接填入 TVBox / 影视仓的「直播地址」，也可用于 APTV、天光云影、我的电视等直播软件。网络收集的直播源稳定性无法保证，IPv6 源需要网络支持 IPv6。

### 直播源仓库

| 项目 | 说明 | ⭐ | 最近更新 |
|---|---|---|---|
| [iptv-org/iptv](https://github.com/iptv-org/iptv) | 全球公开 IPTV 频道合集（按国家 / 语言 / 分类） · [官网](https://iptv-org.github.io) | 143.8k | 2026-11 |
| [imDazui/Tvlist-awesome-m3u-m3u8](https://github.com/imDazui/Tvlist-awesome-m3u-m3u8) | 直播源相关资源汇总（IPTV、M3U） | 30.4k | 2025-11 |
| [fanmingming/live](https://github.com/fanmingming/live) | 可直连访问的电视 / 广播台标库及相关工具 · [官网](https://live.fanmingming.com/) | 28.8k | 2026-11 |
| [Guovin/iptv-api](https://github.com/Guovin/iptv-api) | IPTV 直播源自动更新工具：采集、测速、生成 M3U / TXT，支持 Docker / Actions · [文档](https://guovin.github.io/iptv-api/) | 26.1k | 2026-10 |
| [YanG-1989/m3u](https://github.com/YanG-1989/m3u) | 直播源 | 11.5k | 2026-09 |
| [vbskycn/iptv](https://github.com/vbskycn/iptv) | 最新可用直播源，支持 IPv4 / IPv6 · [官网](https://live.zbds.top/) | 10.3k | 2026-11 |
| [joevess/IPTV](https://github.com/joevess/IPTV) | 自动整合多来源直播源并择优（2024 年后停更） | 10.3k | 2024-12 |
| [HerbertHe/iptv-sources](https://github.com/HerbertHe/iptv-sources) | 自动更新的 IPTV 源 · [官网](https://m3u.ibert.me/) | 9.1k | 2026-11 |
| [ngo5/IPTV](https://github.com/ngo5/IPTV) | IPv4 / IPv6 TVBox 直播点播源收集 | 6.3k | 2026-08 |
| [suxuang/myIPTV](https://github.com/suxuang/myIPTV) | 高清直播源，内置台标与节目预告 | 5.1k | 2026-09 |
| [dongyubin/IPTV](https://github.com/dongyubin/IPTV) | 每月更新的直播源（含体育） | 4.7k | 2026-11 |
| [yuanzl77/IPTV](https://github.com/yuanzl77/IPTV) | 每天自动更新的直播源，IPv4 / IPv6 | 2.1k | 2026-09 |
| [ssili126/tv](https://github.com/ssili126/tv) | 自动收集并测速的 IPv4 酒店直播源，每日更新 | 2k | 2026-11 |
| [kimwang1978/collect-txt](https://github.com/kimwang1978/collect-txt) | 自动整理的直播源（TXT） | 2k | 2026-11 |
| [akiralereal/iptv](https://github.com/akiralereal/iptv) | 自托管 IPTV 直播源管理与分发系统 | 2k | 2026-11 |
| [BurningC4/Chinese-IPTV](https://github.com/BurningC4/Chinese-IPTV) | 央视 / 卫视 IPv4 列表 | 1.7k | 2026-10 |
| [YueChan/Live](https://github.com/YueChan/Live) | 收集于互联网的高清直播源 | 1.5k | 2026-11 |
| [Supprise0901/TVBox_live](https://github.com/Supprise0901/TVBox_live) | 直播源检索、测速、优选 | 1.1k | 2026-11 |
| [zwc456baby/iptv_alive](https://github.com/zwc456baby/iptv_alive) | IPTV 直播源、4K 点播源地址 | 726 | 2026-11 |
| [CCSH/IPTV](https://github.com/CCSH/IPTV) | 直播源、台标、EPG 自动采集同步工具 | 551 | 2026-11 |
| [zhi35/iptv](https://github.com/zhi35/iptv) | 每天自动更新的直播源，IPv4 / IPv6 | 480 | 2026-11 |
| [fuxinyi0505/Ku9-IPTV-source](https://github.com/fuxinyi0505/Ku9-IPTV-source) | 适用于酷9 / 天光云影 / OK影视的直播源 | 109 | 2026-07 |

### EPG 节目单与台标

| 项目 | 说明 | ⭐ | 最近更新 |
|---|---|---|---|
| [iptv-org/epg](https://github.com/iptv-org/epg) | EPG 节目单抓取工具（XMLTV） | 3.5k | 2026-11 |
| [taksssss/iptv-tool](https://github.com/taksssss/iptv-tool) | IPTV 工具箱（Docker）：EPG、直播源与台标管理，兼容 DIYP / 百川、超级直播与 XMLTV 格式 | 1.2k | 2026-10 |
| [suzukua/epg](https://github.com/suzukua/epg) | IPTV 节目单（XMLTV），支持 7 天回看与 5 天预告，每日至少更新两次 · [官网](https://epg.zsdc.eu.org/) | 189 | 2026-11 |
| [kuke31/xmlgz](https://github.com/kuke31/xmlgz) | 国内 EPG 节目单 | 68 | 2026-11 |
| [mytv-android/myEPG](https://github.com/mytv-android/myEPG) | 天光云影项目的聚合 EPG（epg.xml / epg.gz，附 Gitee 镜像） | 41 | 2026-11 |
| [plsy1/epg](https://github.com/plsy1/epg) | 定时从 IPTV 提供商抓取的 EPG | 26 | 2026-11 |
| [xjm1285/epg-server](https://github.com/xjm1285/epg-server) | 把 EPG 节目单转换成 TVBox 可用的接口 | 2 | 2026-02 |

在线 EPG 服务：

- [老张的 EPG](https://epg.51zmt.top:8001/)：2019 年起维护的国内节目单，每天早上更新；XMLTV：`https://epg.51zmt.top:8001/e.xml.gz`，另提供 DIYP 接口。
- [112114 EPG](https://epg.112114.xyz/)：免费无广告；XMLTV：`https://epg.112114.xyz/pp.xml`，另提供 DIYP / 百川、超级直播接口，可自助添加节目、上传台标。
- [epg.pw](https://epg.pw/)：全球节目单服务；中国频道 XMLTV：`https://epg.pw/xmltv/epg_CN.xml`。

## 开发与文档

### 官方文档

- [FongMi 影视使用指南](https://fongmi.github.io/TV/)：含 [App 功能](https://fongmi.github.io/TV/features/)、[播放指令](https://fongmi.github.io/TV/commands/)（可存成播放器按钮的 mpv / Exo 指令）、[配置字典](https://fongmi.github.io/TV/config/)与[爬虫开发](https://fongmi.github.io/TV/spider/)，其中配置字典是目前最完整的配置字段文档。
- [TVBoxOS 配置说明](https://github.com/q215613905/TVBoxOS#readme)：TVBox 分支 README 中的完整 JSON 配置示例与字段注释。
- [FongMi/CatVodSpider](https://github.com/FongMi/CatVodSpider)：Java / Python / QuickJS 爬虫开发模板。
- [drpy 写源教程](https://hjdhnx.github.io/dr_py/doc/%E5%86%99%E6%BA%90%E6%95%99%E7%A8%8B.html)：drpy 规则模板（`var rule = {…}`）的字段说明。

### 入门教程

- [TVBox 电视版下载与安装全流程](https://www.tvbox.org/thread-32957-1-1.html)（TVBox.org）：面向新手，讲解电视版安装包的获取与安装。
- [TVBox 多仓 / 接口导入完整教程](https://www.tvbox.org/thread-33094-1-1.html)（TVBox.org）：单仓、多仓、站点、线路的区别，在线订阅与本地文件导入，以及分级排错。
- [电视软件安装教程](https://www.juwanhezi.com/jc)（聚玩盒子）：按电视、盒子、投影仪品牌分类的第三方应用安装教程。
- [TVBox.org 知识教程版块](https://www.tvbox.org/forum-15-1.html)：更多 TVBox 使用教程。

### 配置文件格式速查

一个最小的点播 + 直播配置（字段以 [FongMi 配置字典](https://fongmi.github.io/TV/config/)为准，各客户端略有差异）：

```json
{
  "spider": "./spider.jar",
  "wallpaper": "https://example.com/wallpaper.jpg",
  "sites": [
    {
      "key": "cms_demo",
      "name": "CMS 采集站",
      "type": 1,
      "api": "https://example.com/api.php/provide/vod/",
      "searchable": 1,
      "quickSearch": 1
    },
    { "key": "java_demo", "name": "Java 爬虫", "type": 3, "api": "csp_Demo" },
    { "key": "js_demo", "name": "JS 爬虫", "type": 3, "api": "./demo.js", "ext": { "region": "cn" } }
  ],
  "parses": [
    { "name": "JSON 解析", "type": 1, "url": "https://example.com/parse?url=" }
  ],
  "lives": [
    {
      "name": "直播",
      "url": "./live.m3u",
      "epg": "https://example.com/epg.xml",
      "logo": "https://example.com/logo/{name}.png"
    }
  ]
}
```

| 字段 | 说明 |
|---|---|
| `spider` | 全局爬虫 JAR 地址；`type: 3` 且 `api` 为 `csp_` 类名的站点从这里加载 |
| `sites` | 点播站点。`type`：0 = XML 采集接口，1 = JSON 采集接口（苹果 CMS 等），3 = 爬虫（Java `csp_` 类 / JS / Python），4 = 远程 HTTP 扩展接口（俗称 T4） |
| `parses` | 解析规则。FongMi 中 `type`：0 = WebView 嗅探，1 = JSON API，2 = JAR JSON，3 = JAR 混合，4 = 并行尝试 |
| `lives` | 直播源，支持 M3U / TXT / JSON，可设置 `epg`、`logo`、`ua` 等 |
| `urls` | 多仓配置，客户端会列出全部仓库供切换（见下例） |
| `doh` / `hosts` / `proxy` / `headers` / `rules` / `ads` | DNS over HTTPS、Host 映射、代理、请求头、嗅探规则、广告域名屏蔽 |

多仓配置：

```json
{
  "urls": [
    { "name": "线路一", "url": "https://example.com/a.json" },
    { "name": "线路二", "url": "https://example.com/b.json" }
  ]
}
```

直播源 TXT 格式（`分组名,#genre#` 开始一个分组，同名频道的多行即多条线路）：

```text
央视频道,#genre#
CCTV-1,https://example.com/cctv1.m3u8
CCTV-1,https://example.com/cctv1_backup.m3u8
卫视频道,#genre#
湖南卫视,https://example.com/hunan.m3u8
```

直播源 M3U 格式：

```text
#EXTM3U x-tvg-url="https://example.com/epg.xml"
#EXTINF:-1 tvg-id="CCTV1" tvg-name="CCTV1" tvg-logo="https://example.com/logo/CCTV1.png" group-title="央视频道",CCTV-1
https://example.com/cctv1.m3u8
```

### 爬虫与源开发

| 项目 | 说明 | ⭐ | 最近更新 |
|---|---|---|---|
| [FongMi/CatVodSpider](https://github.com/FongMi/CatVodSpider) | FongMi 官方爬虫开发模板与示例（Java / Python / QuickJS） | 951 | 2026-11 |
| [hjdhnx/dr_py](https://github.com/hjdhnx/dr_py) | drpy（道长）：网页转 CMS 接口的规则引擎（已归档） · [文档](https://hjdhnx.github.io/dr_py/) | 779 | 2024-05 |
| [jadehh/TVSpider](https://github.com/jadehh/TVSpider) | 影视 / 猫影视爬虫仓库 | 700 | 2024-09 |
| [bizhangjie/CatVodSpider](https://github.com/bizhangjie/CatVodSpider) | TVBox 自定义源接口（CatVodSpider） | 542 | 2025-10 |
| [sec-an/TV_Spider](https://github.com/sec-an/TV_Spider) | TVBoxOSC 服务端爬虫（T4 / Custom Server Spider） | 295 | 2025-08 |
| [syzxasdc/CatVodTVSpider1](https://github.com/syzxasdc/CatVodTVSpider1) | 猫影视 / TVBox / FongMi 自定义爬虫开发调试项目 | 90 | 2024-04 |
| [kknifer7/CatVodSpider-PC](https://github.com/kknifer7/CatVodSpider-PC) | 适配电脑端的猫影视 / TVBox Spider 模板 | 56 | 2025-11 |
| [feg545/maccms10-tvbox-api](https://github.com/feg545/maccms10-tvbox-api) | 苹果 CMS v10 对接 TVBox 接口 | 49 | 2024-08 |
| [hjdhnx/drpy-node-house](https://github.com/hjdhnx/drpy-node-house) | drpyS（drpy-node）源仓库 | 25 | 2026-04 |
| [hjdhnx/drpy3](https://github.com/hjdhnx/drpy3) | drpy3：下一代源规则引擎 | 24 | 2026-10 |
| [hjdhnx/drpy-plugin](https://github.com/hjdhnx/drpy-plugin) | drpyS 插件库（Go 编译跨平台二进制） | 20 | 2026-10 |
| [litan1016/spider-craft](https://github.com/litan1016/spider-craft) | 影视源开发技能包：TVBox / T4 / drpy / WebHome 全流程 | 16 | 2026-09 |

## 实用工具

| 项目 | 说明 | ⭐ | 最近更新 |
|---|---|---|---|
| [power721/alist-tvbox](https://github.com/power721/alist-tvbox) | AList 代理服务，让 TVBox 播放网盘资源（小雅） | 3.2k | 2026-11 |
| [wukongdaily/tvhelper-docker](https://github.com/wukongdaily/tvhelper-docker) | 用电脑 / NAS 上的 Docker 给电视盒子 ADB 装软件 | 1.1k | 2026-03 |
| [hl128k/tvbox](https://github.com/hl128k/tvbox) | 接口域名替换工具 | 820 | 2026-10 |
| [wangrongding/tv-fresh](https://github.com/wangrongding/tv-fresh) | 小米电视去广告 / 清理预装 / 换桌面 / 装影视仓（免 root、可逆） | 773 | 2026-10 |
| [fish2018/tvbox](https://github.com/fish2018/tvbox) | 接口私有化：把 json / jar 保存到自己的 Git 仓库 | 327 | 2025-04 |
| [drizzle888/CatVodTVJsonEditor](https://github.com/drizzle888/CatVodTVJsonEditor) | 猫影视 TV 配置编辑器（早期） | 19 | 2021-12 |
| [outlook84/openlist-tvbox-gateway](https://github.com/outlook84/openlist-tvbox-gateway) | OpenList / AList / WebDAV → TVBox 网关 | 12 | 2026-09 |
| [eastar23/tvbox-manager](https://github.com/eastar23/tvbox-manager) | 把多个接口聚合成多仓 json 并生成链接 | 9 | 2026-04 |
| [hnlyzxf/tvbox-api-jm](https://github.com/hnlyzxf/tvbox-api-jm) | TVBox 接口解密 | 3 | 2026-07 |
| [JinC-Lab/TVBox-Editor](https://github.com/JinC-Lab/TVBox-Editor) | TVBox 接口编辑器 | 2 | 2026-04 |

在线工具：

- [肥猫接口解密](http://xn--z7x900a.net/tool)（`肥猫.net/tool`）：填入接口地址或粘贴密文即可解密，也支持加密与下载 Jar / 本地包。
- [饭太硬加密接口解析](https://fty.888484.xyz/jm/)：解析提取加密的配置接口（域名同上文“饭太硬备用”接口）。
- [秋水网 TVBox 接口解密](https://www.qiushui.vip/gj/jiemi/)：在线解密配置接口。
- [TVBox 配置编辑器](https://z.qiqiv.cn/)：可视化 / 源码两种模式编辑配置，支持配置转图片。
- [M3U 列表格式转换](https://sankei.mo/z.html)：直播源 TXT 与 M3U 格式互转，在浏览器本地完成。
- [gh-proxy.com](https://gh-proxy.com/)：GitHub 文件加速代理，可加速 raw 配置与 Release 下载。属第三方服务，敏感文件慎用。

## 社区与频道

- [TVBoxOSC 频道](https://t.me/TVBoxOSC)（Telegram）：TVBox 自动构建版发布频道。
- [FongMi 影视讨论群](https://t.me/fongmi_official)（Telegram）：FongMi 影视官方讨论群组。
- [WebHomeTV](https://t.me/webhtv)（Telegram）：WebHomeTV 发布与交流。
- [小没用啊](https://space.bilibili.com/503201096/upload/video)（B 站）：盒子软件与接口相关视频。
- [鸭先知&酷啦鱼Ⅰ群](https://qun.qq.com/universal-share/share?ac=1&authKey=7jCQkiAJ1wMBSSASkkAfi7zwCXApT6b2I9KE9UaWpdGkJVYon3YdZ%2B%2B34d7L3cDC&busi_data=eyJncm91cENvZGUiOiI4NTg2Njk1MDQiLCJ0b2tlbiI6InFzV2pWblNjbmgySE84clc5ZGJJWk04T1J5cnp2Ky9nekhlTVc2WnF3d0lQa2pnUkZQaDRVcFpad2FSQ3lzL1UiLCJ1aW4iOiI5NzY2MzY1NSJ9&data=eELPiRTp9gJ3iMA5qJSNZdChqG7tJcQeRjgpEQXlbuKRTw5VtXm2uiZmKEXIwXMWhq7J1-c07LWGR_3Cf9fkKA&svctype=4&tempid=h5_group_info)（QQ 群号 858669504）：盒子软件与接口交流群。
- [zyfun 交流群](https://t.me/+IOovrYLP7gYwYmNl)（Telegram）：zyfun（原 ZyPlayer）README 中给出的交流群。
- [恩山无线论坛 · 智能电视、机顶盒刷机与外贸盒子魔改区](https://www.right.com.cn/forum/forum-281-1.html)：电视盒子刷机、软件与直播源讨论。
- [ZNDS 智能电视网](https://www.znds.com/)：老牌智能电视 / 机顶盒论坛。

## 相关 Awesome 列表

| 项目 | 说明 | ⭐ | 最近更新 |
|---|---|---|---|
| [youhunwl/TVAPP](https://github.com/youhunwl/TVAPP) | 全网 Android TV 盒子应用合集（影视、直播、K 歌、工具等） · [官网](https://app.iyouhun.com) | 28.2k | 2026-11 |
| [laoma528/awesome-zhuiju-free](https://github.com/laoma528/awesome-zhuiju-free) | 免费无广告追剧资源指南（含 TVBox 空壳 / 配置 / IPTV） · [官网](https://zhuiju.me) | 15.4k | 2026-11 |
| [iptv-org/awesome-iptv](https://github.com/iptv-org/awesome-iptv) | IPTV 资源 awesome 清单（英文） | 12.9k | 2026-11 |

## 来源与致谢

- 资源收集自公开网页、GitHub 与社区分享，网站、教程与工具均于 2026-11-12 逐条打开核实。
- 接口状态由脚本于 2026-11-12 抽检（User-Agent `okhttp/3.15`，失败项经 DNS over HTTPS 复核）；GitHub 项目的 Star 数与最近更新时间通过 GitHub API 于同日获取。
- 感谢所有开源作者、接口维护者与资源整理者。

## 参与贡献

欢迎通过 Issue / Pull Request 补充或更正：

1. 每个条目包含名称、链接与一句话说明，放入对应分类；
2. 提交前请确认链接可以访问，失效链接请注明；
3. 不接受付费破解、去广告修改版安装包，以及直接传播盗版内容的链接；
4. 请同步更新中英文 README。

## 许可协议

[CC0 1.0](LICENSE)：在法律允许的范围内，作者放弃本列表的全部版权及相关权利。列表中链接指向的第三方内容仍归各自所有者所有。
