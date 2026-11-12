<div align="center">

# Awesome TVBox

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](LICENSE)
[![Last checked](https://img.shields.io/badge/last%20checked-2026--11--12-blue.svg)](#sources-and-credits)

A curated list of resources for the TVBox / 影视仓 / FongMi ecosystem: clients · config interfaces · live TV sources · developer docs · tools

[简体中文](README.md) | **English**

</div>

> [!WARNING]
> **Disclaimer**: this repository only collects links that are publicly accessible on the internet. It does **not host or distribute** any video content, APK files or config files. TVBox-style apps are empty players that ship without content; whatever a third-party config points to is the responsibility of its provider. Please obey the laws where you live and support official content. This list is for learning and technical research only. For takedown requests, please [open an issue](https://github.com/jiji262/awesome-tvbox/issues).

## Contents

- [What is TVBox](#what-is-tvbox)
- [Quick Start](#quick-start)
- [Clients](#clients)
  - [Open-source Clients](#open-source-clients)
  - [Desktop and Cross-platform](#desktop-and-cross-platform)
  - [Live TV Apps](#live-tv-apps)
  - [Box App Collection](#box-app-collection)
- [Config Interfaces](#config-interfaces)
  - [Preferred Interfaces](#preferred-interfaces)
  - [Backup Interfaces](#backup-interfaces)
  - [Interface Repos on GitHub](#interface-repos-on-github)
  - [Resource and Navigation Sites](#resource-and-navigation-sites)
- [Live TV IPTV](#live-tv-iptv)
  - [Live Source Repos](#live-source-repos)
  - [EPG and Channel Logos](#epg-and-channel-logos)
- [Development and Docs](#development-and-docs)
  - [Official Docs](#official-docs)
  - [Tutorials](#tutorials)
  - [Config Format Cheat Sheet](#config-format-cheat-sheet)
  - [Spider and Source Development](#spider-and-source-development)
- [Tools](#tools)
- [Community](#community)
- [Related Awesome Lists](#related-awesome-lists)
- [Sources and Credits](#sources-and-credits)
- [Contributing](#contributing)
- [License](#license)

## What is TVBox

TVBox is an open-source video app for Android TV boxes, first released as `CatVodTVOfficial/TVBoxOSC` (the original repository has since been deleted); its spider interface follows the CatVod (猫影视) Spider convention. The app itself contains no content: you give it a **config interface** (a JSON URL), and it loads **sites** (MacCMS collection APIs or spiders) for video on demand and **live sources** (M3U / TXT) for live TV.

A large ecosystem has grown around it:

- **Clients**: TVBox forks (takagen99, q215613905, …), FongMi 影视, 影视仓, WebHomeTV, and many repackaged “empty shell” apps;
- **Config interfaces**: community-maintained configs such as 饭太硬, 肥猫, 王二小 and 菜妮丝, shared as single-repo or multi-repo URLs;
- **Live TV**: IPTV source repositories, EPG guides and channel logos;
- **Development**: CatVod spiders (Java / JS / Python), the drpy rule engine, T4 server-side sources, etc.

## Quick Start

1. **Install a client**: pick one from [Clients](#clients) (TV build for TVs / boxes, mobile build for phones). To sideload an APK on a TV, use a USB drive, a TV app store such as [当贝市场 (Dangbei)](https://www.dangbei.com/apps/) or [沙发管家 (Shafa)](https://www.shafa.com/), or ADB over LAN: `adb connect <TV-IP>:5555`, then `adb install app.apk`. See [Tutorials](#tutorials) for brand-specific guides.
2. **Enter a config URL**: open the app, go to **Settings → Config URL** (配置地址), paste a URL from [Config Interfaces](#config-interfaces) and confirm. A multi-repo config (JSON containing `urls`) shows a list of repos to switch between.
3. **Switch sites**: switch the site / data source on the home screen; if playback fails, try another site or line.
4. **Watch live TV**: enter an M3U / TXT live source (see [Live TV IPTV](#live-tv-iptv)) as the live URL (直播地址), or use a config that includes `lives`.

> [!TIP]
> - Chinese domain names may not be typeable or resolvable on some devices; use the Punycode form instead, e.g. `饭太硬.net` → `xn--sss604efuw.net`, `肥猫.net` → `xn--z7x900a.net`. The “Notes” column shows the Chinese domain where applicable.
> - “Image-wrapped” means the config is hidden inside an image file, and “encrypted” means it is encoded; recent clients handle both automatically. If an old client fails to load them, upgrade it.
> - Interfaces break often, so keep a few spares. Statuses below are a snapshot from 2026-11-12 and only show whether the URL was reachable at that time.

## Clients

### Open-source Clients

| Project | Description | ⭐ | Last push |
|---|---|---|---|
| [j4Uq/TVBoxOSC](https://github.com/j4Uq/TVBoxOSC) | Automated TVBox builds (formerly o0HalfLife0o/TVBoxOSC): daily APKs of takagen99/Box, q215613905/TVBoxOS, etc. · [Releases](https://github.com/j4Uq/TVBoxOSC/releases) · [Telegram](https://t.me/TVBoxOSC) | 18.2k | 2026-11 |
| [FongMi/TV](https://github.com/FongMi/TV) | FongMi 影視TV for Android TV, phones and tablets: VOD, live, danmaku, DLNA, web remote; Java / Python / QuickJS spiders · [Guide](https://fongmi.github.io/TV/) · [APK releases](https://github.com/FongMi/Release/releases) · [Telegram](https://t.me/fongmi_official) | 10.5k | 2026-11 |
| [liu673cn/bug](https://github.com/liu673cn/bug) | Open-source TVBox empty shell (unmaintained, for reference) | 10.3k | 2023-12 |
| [takagen99/Box](https://github.com/takagen99/Box) | The takagen99 fork of TVBox | 3.1k | 2026-02 |
| [q215613905/TVBoxOS](https://github.com/q215613905/TVBoxOS) | TVBox fork; README contains a full JSON config example | 3k | 2026-11 |
| [webhtv/webhtv](https://github.com/webhtv/webhtv) | WebHomeTV: FongMi fork with customizable WebHome, cloud-drive link checks · [Telegram](https://t.me/webhtv) | 1.9k | 2026-11 |
| [XiaochangXu/AVBox](https://github.com/XiaochangXu/AVBox) | Multi-platform TVBox redesigned with Material Design 3 | 675 | 2026-11 |
| [motao123/webtv](https://github.com/motao123/webtv) | Android TV client derived from FongMi / CatVod | 201 | 2026-11 |
| [xixu-me/fongmi-tv-actions-builder](https://github.com/xixu-me/fongmi-tv-actions-builder) | GitHub Actions workflow that builds & releases signed FongMi TV APKs | 53 | 2026-10 |
| [zongchenghuan0318/TVBox-fashion-UI](https://github.com/zongchenghuan0318/TVBox-fashion-UI) | Z影视: multi-source client based on TVBoxOSC | 44 | 2026-11 |
| [dhicoc/FusionTV-KitKat](https://github.com/dhicoc/FusionTV-KitKat) | OK影视-based build optimized for old Android 4.4 (ARM32) TVs | 11 | 2026-10 |

> The original TVBox repository `CatVodTVOfficial/TVBoxOSC` has been deleted. Automated builds of its forks are available from [j4Uq/TVBoxOSC Releases](https://github.com/j4Uq/TVBoxOSC/releases).

### Desktop and Cross-platform

| Project | Description | ⭐ | Last push |
|---|---|---|---|
| [Hiram-Wong/zyfun](https://github.com/Hiram-Wong/zyfun) | zyfun (formerly ZyPlayer): cross-platform desktop player supporting TVBox-style sources | 9.1k | 2026-06 |
| [kknifer7/FreeBox](https://github.com/kknifer7/FreeBox) | TVBox for desktop: brings the TVBox ecosystem to PC | 2.1k | 2026-07 |
| [Greatwallcorner/TV-Multiplatform](https://github.com/Greatwallcorner/TV-Multiplatform) | Desktop implementation based on FongMi/TV | 718 | 2026-01 |
| [hgtuj5688/tvbox-desktop](https://github.com/hgtuj5688/tvbox-desktop) | TVBox Desktop: minimal Windows client that imports TVBox config subscriptions; M3U / TXT live TV | 359 | 2026-09 |
| [yagami-hue/Win-box](https://github.com/yagami-hue/Win-box) | TVBox for Windows | 350 | 2026-11 |
| [yuluoos/TVBox-tvs](https://github.com/yuluoos/TVBox-tvs) | TVS: Flutter shell player for Android TV / iOS / iPadOS / macOS; supports PeekPro subscriptions and M3U / TXT / JSON live sources only, TVBox configs not guaranteed · [Downloads](https://yuluoos.github.io/TVBox-tvs/) | 240 | 2026-11 |
| [sky22333/sky-tv](https://github.com/sky22333/sky-tv) | Cross-platform player for custom VOD and IPTV sources | 139 | 2026-10 |
| [yaolin-dev/OKVideoMac](https://github.com/yaolin-dev/OKVideoMac) | Native macOS (Apple Silicon) IPTV/VOD player | 124 | 2026-11 |
| [cwe88108/free-new-desk-public](https://github.com/cwe88108/free-new-desk-public) | TVBox/FongMi-style desktop player for Windows 11 x64 | 121 | 2026-10 |
| [zhujinrun/FongMi-Player](https://github.com/zhujinrun/FongMi-Player) | Cross-platform desktop player parsing mainstream TVBox sources | 32 | 2026-11 |
| [LanLanff/FlyTV](https://github.com/LanLanff/FlyTV) | TVBox for Windows, portable; cloud-drive playback, danmaku, history sync | 28 | 2026-11 |
| [jianbinzhang1987/OKPlayer](https://github.com/jianbinzhang1987/OKPlayer) | Cross-platform desktop player compatible with FongMi / TVBox configs | 17 | 2026-11 |
| [tengdechun/tvbox-desktop](https://github.com/tengdechun/tvbox-desktop) | TVBox / CatVod-compatible Windows desktop client | 12 | 2026-08 |
| [shareu007/tvbox-Swift-macOS](https://github.com/shareu007/tvbox-Swift-macOS) | Native SwiftUI TVBox client for macOS / iOS | 9 | 2026-10 |
| [wj5403293/KOTV](https://github.com/wj5403293/KOTV) | Flutter / Go cross-platform client compatible with CatVod configs | 6 | 2026-08 |

### Live TV Apps

| Project | Description | ⭐ | Last push |
|---|---|---|---|
| [lizongying/my-tv](https://github.com/lizongying/my-tv) | my-tv: install-and-watch live TV app (inactive since 2024) | 32k | 2024-06 |
| [lizongying/my-tv-0](https://github.com/lizongying/my-tv-0) | my-tv-0: live TV app with custom sources | 4.7k | 2025-05 |
| [mytv-android/mytv-android](https://github.com/mytv-android/mytv-android) | 天光云影 (mytv): Material 3 Expressive IPTV player for Android / Android TV · [Docs](https://mytv-android.github.io/mytv-doc/) | 3.1k | 2026-11 |
| [Kimentanm/aptv](https://github.com/Kimentanm/aptv) | APTV: IPTV player for iOS / iPadOS / tvOS / macOS / watchOS with M3U, catch-up and EPG · [App Store](https://apps.apple.com/cn/app/aptv/id1630403500) | 2.9k | 2026-11 |
| [yaoxieyoulei/mytv-android](https://github.com/yaoxieyoulei/mytv-android) | Original 天光云影 project (archived) | 1.9k | 2025-09 |
| [HTWMedia/HTV](https://github.com/HTWMedia/HTV) | Free ad-free live TV app for phones and TV boxes | 832 | 2026-11 |

### Box App Collection

Versions and dates for the 31 apps below are as of 2026-11-12; download links are Quark / Guangya cloud-drive shares. Three modified builds (ad-removed / premium) are listed without download links. Most of these are closed-source third-party builds, so judge their safety before installing.

| App | Version | Platform | Description | Updated | Download |
|---|---|---|---|---|---|
| 橘汁 | 3.0.7.1 (ad-free mod) | Android | VOD app for Android phone & TV, HD sources | 2026-11-11 | Modified build, not linked |
| 免费电视 | 261012 | Android | Live TV channels | 2026-11-04 | [Quark](https://pan.quark.cn/s/39c87e087ff0) · [Guangya](https://www.guangyapan.com/s/1965091076424675358_aeoR4oULFG4aU0pK) |
| 归零box | 1.5.13 | TV | TVBox-based VOD & live TV player | 2026-11-04 | [Quark](https://pan.quark.cn/s/62834910c0f9) · [Guangya](https://www.guangyapan.com/s/1965091202564161578_aeoR4oULFG4aU0pK) |
| 高清直播 | 1.1.2 | TV | HD live TV channel player | 2026-11-04 | [Quark](https://pan.quark.cn/s/3bc9e450c24c) · [Guangya](https://www.guangyapan.com/s/1965091225150500915_aeoR4oULFG4aU0pK) |
| 电视家 | 9.9.9 | TV | Free live CCTV & satellite channels | 2026-11-04 | [Quark](https://pan.quark.cn/s/1337ca2f056e) · [Guangya](https://www.guangyapan.com/s/1965091293429518386_aeoR4oULFG4aU0pK) |
| 影视仓 | 6.2.9 | TV | TVBox fork, empty shell (bring your own config) | 2026-11-04 | [Quark](https://pan.quark.cn/s/154038a9cbaa) · [Guangya](https://www.guangyapan.com/s/1953049516944642140_aeoR4oULFG4aU0pK) |
| 默影视 | 5.6.0 | Android / TV | VOD + live, empty shell, TVBox-config compatible | 2026-11-04 | [Quark](https://pan.quark.cn/s/5b20c49599e3) · [Guangya](https://www.guangyapan.com/s/1941113271887003656_aeoR4oULFG4aU0pK) |
| 超级直播 | 3.2.0 | Android | Live TV, clean & ad-free | 2026-10-28 | [Quark](https://pan.quark.cn/s/f974d506bd84) · [Guangya](https://www.guangyapan.com/s/1945878610387382353_aeoR4oULFG4aU0pK) |
| NewBox | 2.1.1 | TV | VOD + live, empty shell, TVBox-config compatible | 2026-10-27 | [Quark](https://pan.quark.cn/s/4c875099c325) · [Guangya](https://www.guangyapan.com/s/1936828671156740158_aeoR4oULFG4aU0pK) |
| FongMi影视 | 5.8.4 | TV | Built on the open-source CatVod project | 2026-10-27 | [Quark](https://pan.quark.cn/s/52095963630b) · [Guangya](https://www.guangyapan.com/s/1941081829538717706_aeoR4oULFG4aU0pK) |
| 天下直播 | 3.1.1 | TV | Live TV app | 2026-10-07 | [Quark](https://pan.quark.cn/s/90ba5c0c93b3) · [Guangya](https://www.guangyapan.com/s/1954901836208779270_aeoR4oULFG4aU0pK) |
| 蝴蝶影院 | 5.0.0 | TV | Box app with a rich movie/series library | 2026-10-06 | [Quark](https://pan.quark.cn/s/3cf740bc3854) · [Guangya](https://www.guangyapan.com/s/1954402126582747218_aeoR4oULFG4aU0pK) |
| WebHomeTV | 5.6.0 | TV | VOD + live, empty shell, TVBox-config compatible | 2026-10-02 | [Quark](https://pan.quark.cn/s/dafac8daa686) · [Guangya](https://www.guangyapan.com/s/1941882633636270121_aeoR4oULFG4aU0pK) |
| 星河TV | 2.0.355 | Android | Multi-channel player, low latency | 2026-10-02 | [Quark](https://pan.quark.cn/s/aa6c08a75b44) · [Guangya](https://www.guangyapan.com/s/1944067664597577758_aeoR4oULFG4aU0pK) |
| 电视影院TV | 9.1 | TV | Built-in sources, free sign-up | 2026-09-21 | [Quark](https://pan.quark.cn/s/801c3bd67ac6) · [Guangya](https://www.guangyapan.com/s/1949118544087859211_aeoR4oULFG4aU0pK) |
| 星火电视 | 1.0.53.1 | TV | Movies, documentaries, recipes, galas, concerts, music | 2026-09-21 | [Quark](https://pan.quark.cn/s/8c87fd7bbbc6) · [Guangya](https://www.guangyapan.com/s/1949118566921633837_aeoR4oULFG4aU0pK) |
| 星落 | 6.0.0.6 | TV | TVBox-config compatible, phone & TV builds | 2026-09-20 | [Quark](https://pan.quark.cn/s/1e4ce4ce4c00) · [Guangya](https://www.guangyapan.com/s/1937165723928780867_aeoR4oULFG4aU0pK) |
| 青龙TV | 1.0.0 | TV | Ad-free live TV app | 2026-09-17 | [Quark](https://pan.quark.cn/s/7f5713f40bd7) · [Guangya](https://www.guangyapan.com/s/1947673428349116436_aeoR4oULFG4aU0pK) |
| TVBox | 20260914 | TV | Original TVBox (Q build), empty shell | 2026-09-15 | [Quark](https://pan.quark.cn/s/6f98da0cfe6a) · [Guangya](https://www.guangyapan.com/s/1941082816995323952_aeoR4oULFG4aU0pK) |
| uzn | 1.1.8 | Android / Windows / iOS / macOS | VOD + live empty shell, configs bundled with download | 2026-09-13 | [Quark](https://pan.quark.cn/s/66f5d84631f6) · [Guangya](https://www.guangyapan.com/s/1945915658997579844_aeoR4oULFG4aU0pK) |
| 网视TV | 1.0.0 | TV | — | 2026-09-12 | [Quark](https://pan.quark.cn/s/a96426a0ebf8) · [Guangya](https://www.guangyapan.com/s/1945868041672437815_aeoR4oULFG4aU0pK) |
| 星视TV | 1.3.4 | TV | — | 2026-09-12 | [Quark](https://pan.quark.cn/s/3fae3afb0440) · [Guangya](https://www.guangyapan.com/s/1939014577938800708_aeoR4oULFG4aU0pK) |
| PeekPro | 1.5.7 | Android / Windows / iOS | — | 2026-09-06 | [Quark](https://pan.quark.cn/s/2ab3e47ab079) · [Guangya](https://www.guangyapan.com/s/1941112278587773009_aeoR4oULFG4aU0pK) |
| 星微短剧 | 828 | Android / TV | — | 2026-08-31 | [Quark](https://pan.quark.cn/s/efee3dcfb6eb) · [Guangya](https://www.guangyapan.com/s/1941542559530754095_aeoR4oULFG4aU0pK) |
| 智哥影视 | 2.8.9 | TV | — | 2026-08-30 | [Quark](https://pan.quark.cn/s/a2a2b4406466) · [Guangya](https://www.guangyapan.com/s/1941113547586965521_aeoR4oULFG4aU0pK) |
| 魄狼TV | 1.0.7 | TV | — | 2026-08-30 | [Quark](https://pan.quark.cn/s/7e428118e868) · [Guangya](https://www.guangyapan.com/s/1941113371342340190_aeoR4oULFG4aU0pK) |
| 畅映TV | 1.9.0 (ad-free mod) | Android | — | 2026-08-22 | Modified build, not linked |
| 电影侠 | 3.5.0 | TV | — | 2026-08-19 | [Quark](https://pan.quark.cn/s/8ee87d237d6c) · [Guangya](https://www.guangyapan.com/s/1937161724152426532_aeoR4oULFG4aU0pK) |
| GD影视 | 5.4.1.13 | TV | — | 2026-08-18 | [Quark](https://pan.quark.cn/s/629b7a9993fb) · [Guangya](https://www.guangyapan.com/s/1936828432714727505_aeoR4oULFG4aU0pK) |
| 宸龙影视 | 5.6.0 | Android / TV | — | 2026-08-17 | [Quark](https://pan.quark.cn/s/fb75db7f0514) · [Guangya](https://www.guangyapan.com/s/1936440748947198017_aeoR4oULFG4aU0pK) |
| 追光影院 | 9.94 (premium mod) | TV | — | 2026-08-16 | Modified build, not linked |

## Config Interfaces

Paste a “Config URL” below into your client's config setting. Status legend: ✅ reachable (plain JSON, image-wrapped or encrypted); ⚠️ blocked (HTTPS handshake failed; may only work on some networks); ❌ dead (DNS failure or HTTP 404 / 403).

### Preferred Interfaces

| Name | Notes | Config URL | Status |
|---|---|---|---|
| 王二小 | Mixed, mostly cloud-drive 4K; for cloud-drive VIP users | `https://9280.kstore.vip/newwex.json` | ✅ |
| 菜妮丝 | Regular; recommended: Guazi, Jinpai (= `tv.菜妮丝.top`) | `https://tv.xn--yhqu5zs87a.top` | ✅ |
| 饭太硬 | Mixed; recommended: Jianpian | `http://www.饭太硬.net/tv` | ✅ image-wrapped |
| 肥猫 | Mixed; recommended: Feimao, Guazi, Jinpai | `http://肥猫.net/` | ✅ encrypted |
| 少儿频道 | Kids & education (preschool to high school) | `https://jihulab.com/ymz1231/xymz/-/raw/main/ymshaoer` | ✅ image-wrapped |
| 俊哥 | Regular sources | `http://home.jundie.top:81/top98.json` | ✅ |
| 小盒子 | Regular sources | `http://xhztv.top/xhz` | ✅ |
| 4k云盘接口 | Mixed, low availability | `https://9xi4o.tk/0725.json` | ❌ DNS failed |
| 无意云 | Mixed; without a cloud drive, pick lower-ranked lines (higher quality) | `https://ym.wya6.cn/` | ❌ DNS failed |
| 欧歌接口 | Regular VOD sources (= `sd欧歌ds.v.nxog.top`) | `https://xn--sdds-rp5imh.v.nxog.top/apitv.php?id=3` | ⚠️ blocked/SSL |

### Backup Interfaces

| Name | Notes | Config URL | Status |
|---|---|---|---|
| 小盒子4K | 4K HD sources | `http://xhztv.top/4k.json` | ✅ |
| 少儿频道 | Kids & education (preschool to high school) | `https://jihulab.com/ymz1231/xymz/-/raw/main/ymshaoer` | ✅ image-wrapped |
| 二月红接口 | General VOD sources | `https://700sjro44343.vicp.fun/eggp/0211/tv.json` | ✅ |
| 俊哥接口 | Regular sources | `http://home.jundie.top:81/top98.json` | ✅ |
| 欧歌免费 | Ouge free public sources | `https://tv.nxog.top/m/111.php?ou=公众号欧歌app&mz=index&jar=index&123&b=tv` | ⚠️ blocked/SSL |
| 王二小接口 | Wang Erxiao backup (= `tvbox.王二小放牛娃.top`) | `http://tvbox.xn--4kq62z5rby2qupq9ub.top/` | ✅ |
| 王二小放牛娃 | Wang Erxiao cloud-drive backup | `http://tv.999888987.xyz` | ✅ |
| 饭太硬 | Mixed; recommended: Jianpian | `https://qist.wyfc.qzz.io/fty.json` | ✅ |
| 潇洒 | General HD sources | `https://qist.wyfc.qzz.io/xiaosa/api.json` | ✅ |
| 牛二 | Cloud-drive 4K mixed | `https://9280.kstore.space/newwex.json` | ✅ |
| uuccc | General VOD sources (= `影视仓.com`) | `http://xn--5mqx81b535a.com/` | ✅ |
| fmys | Aggregated sources | `http://fmys.top/fmys.json` | ❌ 404 |
| 饭太硬备用 | Fantaiying backup address | `https://fty.888484.xyz/tv` | ✅ image-wrapped |
| 新接口 | New aggregated source | `https://www.iyouhun.com/tv/wex` | ✅ |
| ok线路1 | Stable general VOD source | `https://raw.liucn.cc/box/m.json` | ✅ |
| 荐片 | Jianpian HD source | `https://tv.203511.xyz/0821.json` | ✅ |
| my interface | Self-hosted interface | `http://124.223.214.31:8/api.json` | ✅ |
| 1号VIP源 | VIP-tier VOD sources | `https://700sjro44343.vicp.fun/vip/vip/tv.json` | ✅ |
| 软件内置源 | Built-in source (port service) | `http://47.96.82.41:5188/api.json` | ✅ |
| ok线路2 | Backup hosted on GitHub Gist | `https://gist.githubusercontent.com/ph7368/20ee6c7b64d77d82f8f4162cdd04ad61/raw/gistfile1.txt` | ✅ |
| 11号托管源 | GitHub static mirror (jsDelivr) | `https://cdn.jsdelivr.net/gh/liu673cn/box@main/m.json` | ✅ |
| 摸鱼儿 | Source for "Fish" player | `https://6800.kstore.vip/fish.json` | ✅ |
| sss公用源 | Long-term stable public source (= `饭太硬.net`) | `http://www.xn--sss604efuw.net/tv` | ✅ image-wrapped |
| 牛儿 | Backup wex source (same site as Niu Er) | `https://9280.kstore.space/wex.json` | ✅ |
| 拾光 | SVIP HD hosted source | `https://gh-proxy.com/https://raw.githubusercontent.com/xmbjm/svip/refs/heads/main/svip.json` | ✅ |
| 神秘大佬 | Aggregated source via GitHub proxy | `https://g.33445500.xyz/https://raw.githubusercontent.com/qist/tvbox/refs/heads/master/jsm.json` | ✅ |
| 潇洒Github备用 | Xiaosa mirror via GitHub proxy | `https://g.33445500.xyz/https://raw.githubusercontent.com/qist/tvbox/refs/heads/master/xiaosa/api.json` | ✅ |
| 小苹果线路 | Xiaopingguo source on Bitbucket | `https://bitbucket.org/xduo/duoapi/raw/master/xpg.json` | ❌ 404 |
| 66号GitCode源 | Static interface on GitCode (CN) | `https://raw.gitcode.com/jvftibcs-jbduyh/021/raw/main/18.json` | ❌ 403 |
| 金鹰 | Jinying aggregated source | `http://550.3vcn.work/wdjyys.json` | ✅ |

### Interface Repos on GitHub

Community-maintained config repositories. Their READMEs usually list single-repo / multi-repo URLs, and some update automatically via GitHub Actions.

| Project | Description | ⭐ | Last push |
|---|---|---|---|
| [qist/tvbox](https://github.com/qist/tvbox) | OK影视 & TVBox configs (multi/single repo, jars) | 12.8k | 2026-11 |
| [gaotianliuyun/gao](https://github.com/gaotianliuyun/gao) | FongMi & TVBox configs (inactive since 2024) | 8.2k | 2024-11 |
| [2hacc/TVBox](https://github.com/2hacc/TVBox) | TVBox interfaces (inactive since 2024) | 5.9k | 2024-12 |
| [noimank/tvbox](https://github.com/noimank/tvbox) | Personal TVBox sources, multi-repo configs & notes | 3.7k | 2026-08 |
| [xianyuyimu/TVBOX-](https://github.com/xianyuyimu/TVBOX-) | Yimu personal TVBox repo | 3.1k | 2026-09 |
| [Zhou-Li-Bin/Tvbox-QingNing](https://github.com/Zhou-Li-Bin/Tvbox-QingNing) | QingNing: TVBox / 影视仓 interfaces & live sources (single / multi repo) · [Website](https://132130.com) | 2.1k | 2026-11 |
| [Dong-learn9/TVBox-zyjk](https://github.com/Dong-learn9/TVBox-zyjk) | Personal TVBox interfaces | 1.6k | 2025-01 |
| [jinenge/tvbox](https://github.com/jinenge/tvbox) | Built-in sources for TVBox / 影视仓, kept updated | 1.2k | 2026-06 |
| [xiongjian83/TvBox](https://github.com/xiongjian83/TvBox) | TVBox interfaces | 702 | 2026-11 |
| [cluntop/tvbox](https://github.com/cluntop/tvbox) | TVBox interfaces / OK影视 | 675 | 2026-11 |
| [yangxiaoge/tvbox_cust](https://github.com/yangxiaoge/tvbox_cust) | Custom TVBox configs (author: personal use only) | 634 | 2026-11 |
| [wuxierj/TVBox](https://github.com/wuxierj/TVBox) | TVBox & 影视仓 interface list | 418 | 2026-05 |
| [Lightconer/tvbox-ysc-config](https://github.com/Lightconer/tvbox-ysc-config) | Aggregated configs auto-updated daily via GitHub Actions (肥猫 / 饭太硬 / 王二小, …) | 397 | 2026-11 |
| [kimwang1978/tvbox](https://github.com/kimwang1978/tvbox) | Personal 影视仓 / TVBox configs | 396 | 2025-11 |
| [CandyMuj/ResourceInterface](https://github.com/CandyMuj/ResourceInterface) | Interfaces for various apps (TVBox, Legado, …) | 304 | 2026-11 |
| [ne7359/tvurl](https://github.com/ne7359/tvurl) | OK影视 & TVBox configs | 301 | 2026-11 |
| [yoursmile66/TVBox](https://github.com/yoursmile66/TVBox) | TVBox interfaces (json + jar + live list) | 258 | 2026-11 |
| [niubihu1/tvbox](https://github.com/niubihu1/tvbox) | Niuhu aggregated TVBox interfaces (single & multi repo) | 225 | 2026-11 |
| [mrgaoshuiquan/tvbox-config](https://github.com/mrgaoshuiquan/tvbox-config) | Personal config based on 饭太硬 | 155 | 2026-08 |
| [chendi0207/my-TVBOX](https://github.com/chendi0207/my-TVBOX) | TVBox interfaces collected from the web | 150 | 2026-11 |
| [TVboxorg/TVbox](https://github.com/TVboxorg/TVbox) | TVBox interface list with availability probing · [Website](https://www.tvbox.org/) | 26 | 2026-11 |
| [jiusanzhou/tvbox](https://github.com/jiusanzhou/tvbox) | Merges multiple sites into one subscription URL | 22 | 2026-11 |
| [shengshimeiyan/fty44safe](https://github.com/shengshimeiyan/fty44safe) | Interface for Android 4.4 boxes (no spider jar, type:1 only) | 12 | 2026-09 |
| [dxyc0922/Tvbox4.x_api](https://github.com/dxyc0922/Tvbox4.x_api) | TVBox interface for old Android 4.x devices | 8 | 2026-11 |

### Resource and Navigation Sites

Popular resource sites:

| Site | Notes |
|---|---|
| [口袋猫](https://www.kdmao.com/category/tv) | TV box apps, updated regularly |
| [小盒子工具箱](https://www.xhztv.pro/) | Apps & interfaces: collection, updates, DIY |
| [江江TVBox](https://tv.xn--9swa.com/) | TVBox & IPTV interface collection (`tv.江江.com`) |
| [硬核指南TvBox](https://yinghezhinan.com/tvbox-jsonlist/) | TVBox interface collection |

More interface navigation and aggregator sites (in Chinese):

- [聚玩盒子 · 数据源](https://www.juwanhezi.com/jsonlist): single-repo / multi-repo / local-pack interface lists with a per-entry availability probe; the same site also has a [live source list](https://www.juwanhezi.com/live).
- [硬核指南 · 影视仓配置接口](https://yinghezhinan.com/yingshicang-jiekou/): same site as "硬核指南TvBox" above; single- and multi-repo interfaces with notes.
- [源仓库 (yckceo)](https://www.yckceo.com/index/applist/tvbox.html): TVBox client notes and an index of interfaces from many maintainers.
- [资源收藏夹 · TV盒子与直播](https://zyscj.com/zy/video/tv.html): hand-curated links to box apps, interfaces and live sources.

## Live TV IPTV

Live sources are usually M3U / TXT files. Use them as the live URL in TVBox / 影视仓, or in live TV apps such as APTV, 天光云影 (mytv) and 我的电视 (my-tv). Sources collected from the web are not guaranteed to be stable, and IPv6 sources require IPv6 connectivity.

### Live Source Repos

| Project | Description | ⭐ | Last push |
|---|---|---|---|
| [iptv-org/iptv](https://github.com/iptv-org/iptv) | Global collection of publicly available IPTV channels · [Website](https://iptv-org.github.io) | 143.8k | 2026-11 |
| [imDazui/Tvlist-awesome-m3u-m3u8](https://github.com/imDazui/Tvlist-awesome-m3u-m3u8) | Curated IPTV / M3U resources | 30.4k | 2025-11 |
| [fanmingming/live](https://github.com/fanmingming/live) | Directly accessible TV / radio logo library & tools · [Website](https://live.fanmingming.com/) | 28.8k | 2026-11 |
| [Guovin/iptv-api](https://github.com/Guovin/iptv-api) | IPTV source updater: crawl, speed-test, output M3U/TXT; Docker & Actions · [Docs](https://guovin.github.io/iptv-api/) | 26.1k | 2026-10 |
| [YanG-1989/m3u](https://github.com/YanG-1989/m3u) | Live sources | 11.5k | 2026-09 |
| [vbskycn/iptv](https://github.com/vbskycn/iptv) | Latest working live sources, IPv4 / IPv6 · [Website](https://live.zbds.top/) | 10.3k | 2026-11 |
| [joevess/IPTV](https://github.com/joevess/IPTV) | Aggregates and picks the best live streams (inactive since 2024) | 10.3k | 2024-12 |
| [HerbertHe/iptv-sources](https://github.com/HerbertHe/iptv-sources) | Auto-updated IPTV sources · [Website](https://m3u.ibert.me/) | 9.1k | 2026-11 |
| [ngo5/IPTV](https://github.com/ngo5/IPTV) | IPv4 / IPv6 TVBox live & VOD sources | 6.3k | 2026-08 |
| [suxuang/myIPTV](https://github.com/suxuang/myIPTV) | HD live sources with logos & EPG | 5.1k | 2026-09 |
| [dongyubin/IPTV](https://github.com/dongyubin/IPTV) | Monthly-updated live sources (incl. sports) | 4.7k | 2026-11 |
| [yuanzl77/IPTV](https://github.com/yuanzl77/IPTV) | Daily auto-updated live sources, IPv4 / IPv6 | 2.1k | 2026-09 |
| [ssili126/tv](https://github.com/ssili126/tv) | Auto-collected, speed-tested IPv4 hotel IPTV sources, daily | 2k | 2026-11 |
| [kimwang1978/collect-txt](https://github.com/kimwang1978/collect-txt) | Auto-curated live sources (TXT) | 2k | 2026-11 |
| [akiralereal/iptv](https://github.com/akiralereal/iptv) | Self-hosted IPTV source management & distribution | 2k | 2026-11 |
| [BurningC4/Chinese-IPTV](https://github.com/BurningC4/Chinese-IPTV) | CCTV & provincial channel list (IPv4) | 1.7k | 2026-10 |
| [YueChan/Live](https://github.com/YueChan/Live) | HD live sources collected from the web | 1.5k | 2026-11 |
| [Supprise0901/TVBox_live](https://github.com/Supprise0901/TVBox_live) | Live source search, speed test & selection | 1.1k | 2026-11 |
| [zwc456baby/iptv_alive](https://github.com/zwc456baby/iptv_alive) | IPTV live & 4K VOD source URLs | 726 | 2026-11 |
| [CCSH/IPTV](https://github.com/CCSH/IPTV) | Auto collector for live sources, logos & EPG | 551 | 2026-11 |
| [zhi35/iptv](https://github.com/zhi35/iptv) | Daily auto-updated live sources, IPv4 / IPv6 | 480 | 2026-11 |
| [fuxinyi0505/Ku9-IPTV-source](https://github.com/fuxinyi0505/Ku9-IPTV-source) | Live sources for 酷9 / 天光云影 / OK影视 | 109 | 2026-07 |

### EPG and Channel Logos

| Project | Description | ⭐ | Last push |
|---|---|---|---|
| [iptv-org/epg](https://github.com/iptv-org/epg) | EPG grabber utilities (XMLTV) | 3.5k | 2026-11 |
| [taksssss/iptv-tool](https://github.com/taksssss/iptv-tool) | IPTV toolbox (Docker): manage EPG, live sources and logos; DIYP / Baichuan, 超级直播 and XMLTV formats | 1.2k | 2026-10 |
| [suzukua/epg](https://github.com/suzukua/epg) | IPTV EPG (XMLTV) with 7-day catch-up and 5-day preview, updated at least twice a day · [Website](https://epg.zsdc.eu.org/) | 189 | 2026-11 |
| [kuke31/xmlgz](https://github.com/kuke31/xmlgz) | Chinese EPG data | 68 | 2026-11 |
| [mytv-android/myEPG](https://github.com/mytv-android/myEPG) | Aggregated EPG from the mytv-android project (epg.xml / epg.gz, Gitee mirror) | 41 | 2026-11 |
| [plsy1/epg](https://github.com/plsy1/epg) | EPG scraped from IPTV providers on schedule | 26 | 2026-11 |
| [xjm1285/epg-server](https://github.com/xjm1285/epg-server) | Converts EPG into a TVBox-compatible API | 2 | 2026-02 |

Online EPG services:

- [老张的 EPG](https://epg.51zmt.top:8001/): Chinese EPG maintained since 2019 and updated every morning; XMLTV: `https://epg.51zmt.top:8001/e.xml.gz`, plus a DIYP API.
- [112114 EPG](https://epg.112114.xyz/): free and ad-free; XMLTV: `https://epg.112114.xyz/pp.xml`, plus DIYP / Baichuan and 超级直播 APIs, with self-service programme additions and logo uploads.
- [epg.pw](https://epg.pw/): worldwide EPG service; China XMLTV: `https://epg.pw/xmltv/epg_CN.xml`.

## Development and Docs

### Official Docs

- [FongMi 影视 Guide](https://fongmi.github.io/TV/): [app features](https://fongmi.github.io/TV/features/), [player commands](https://fongmi.github.io/TV/commands/) (mpv / Exo commands you can save as player buttons), the [config dictionary](https://fongmi.github.io/TV/config/) and [spider development](https://fongmi.github.io/TV/spider/); the config dictionary is currently the most complete reference for config fields.
- [TVBoxOS config notes](https://github.com/q215613905/TVBoxOS#readme): a full annotated JSON config example in a TVBox fork's README.
- [FongMi/CatVodSpider](https://github.com/FongMi/CatVodSpider): spider templates for Java / Python / QuickJS.
- [drpy rule-writing guide](https://hjdhnx.github.io/dr_py/doc/%E5%86%99%E6%BA%90%E6%95%99%E7%A8%8B.html) (Chinese): field reference for the drpy rule template (`var rule = {…}`).

### Tutorials

All in Chinese:

- [TVBox TV edition: download and install](https://www.tvbox.org/thread-32957-1-1.html) (TVBox.org): a beginner's guide to getting the TV build and installing it.
- [TVBox multi-repo / interface import guide](https://www.tvbox.org/thread-33094-1-1.html) (TVBox.org): single vs. multi-repo, sites vs. routes, URL and local-file import, and layered troubleshooting.
- [TV app installation guides](https://www.juwanhezi.com/jc) (聚玩盒子): sideloading guides organized by TV, box and projector brand.
- [TVBox.org tutorials board](https://www.tvbox.org/forum-15-1.html): more TVBox how-tos.

### Config Format Cheat Sheet

A minimal VOD + live config (fields follow the [FongMi config dictionary](https://fongmi.github.io/TV/config/); clients differ slightly):

```json
{
  "spider": "./spider.jar",
  "wallpaper": "https://example.com/wallpaper.jpg",
  "sites": [
    {
      "key": "cms_demo",
      "name": "CMS site",
      "type": 1,
      "api": "https://example.com/api.php/provide/vod/",
      "searchable": 1,
      "quickSearch": 1
    },
    { "key": "java_demo", "name": "Java spider", "type": 3, "api": "csp_Demo" },
    { "key": "js_demo", "name": "JS spider", "type": 3, "api": "./demo.js", "ext": { "region": "cn" } }
  ],
  "parses": [
    { "name": "JSON parser", "type": 1, "url": "https://example.com/parse?url=" }
  ],
  "lives": [
    {
      "name": "Live",
      "url": "./live.m3u",
      "epg": "https://example.com/epg.xml",
      "logo": "https://example.com/logo/{name}.png"
    }
  ]
}
```

| Field | Description |
|---|---|
| `spider` | Global spider JAR; `type: 3` sites whose `api` is a `csp_` class name are loaded from it |
| `sites` | VOD sites. `type`: 0 = XML collection API, 1 = JSON collection API (MacCMS etc.), 3 = spider (Java `csp_` class / JS / Python), 4 = remote HTTP extension API (a.k.a. T4) |
| `parses` | URL parsers. In FongMi, `type`: 0 = WebView sniffing, 1 = JSON API, 2 = JAR JSON, 3 = JAR mixed, 4 = parallel |
| `lives` | Live sources in M3U / TXT / JSON, with optional `epg`, `logo`, `ua`, … |
| `urls` | Multi-repo config; the client lists every repo for switching (see below) |
| `doh` / `hosts` / `proxy` / `headers` / `rules` / `ads` | DNS over HTTPS, host mapping, proxies, request headers, sniffing rules, ad-domain blocking |

Multi-repo config:

```json
{
  "urls": [
    { "name": "Line 1", "url": "https://example.com/a.json" },
    { "name": "Line 2", "url": "https://example.com/b.json" }
  ]
}
```

Live source TXT format (`group,#genre#` starts a group; repeated channel names become alternative lines):

```text
央视频道,#genre#
CCTV-1,https://example.com/cctv1.m3u8
CCTV-1,https://example.com/cctv1_backup.m3u8
卫视频道,#genre#
湖南卫视,https://example.com/hunan.m3u8
```

Live source M3U format:

```text
#EXTM3U x-tvg-url="https://example.com/epg.xml"
#EXTINF:-1 tvg-id="CCTV1" tvg-name="CCTV1" tvg-logo="https://example.com/logo/CCTV1.png" group-title="CCTV",CCTV-1
https://example.com/cctv1.m3u8
```

### Spider and Source Development

| Project | Description | ⭐ | Last push |
|---|---|---|---|
| [FongMi/CatVodSpider](https://github.com/FongMi/CatVodSpider) | Official FongMi spider template & demos (Java / Python / QuickJS) | 951 | 2026-11 |
| [hjdhnx/dr_py](https://github.com/hjdhnx/dr_py) | drpy: rule engine converting sites to CMS APIs (archived) · [Docs](https://hjdhnx.github.io/dr_py/) | 779 | 2024-05 |
| [jadehh/TVSpider](https://github.com/jadehh/TVSpider) | Spiders for 影视 / CatVod | 700 | 2024-09 |
| [bizhangjie/CatVodSpider](https://github.com/bizhangjie/CatVodSpider) | Custom TVBox source spiders | 542 | 2025-10 |
| [sec-an/TV_Spider](https://github.com/sec-an/TV_Spider) | Server-side spider for TVBoxOSC (T4) | 295 | 2025-08 |
| [syzxasdc/CatVodTVSpider1](https://github.com/syzxasdc/CatVodTVSpider1) | CatVod / TVBox / FongMi spider dev & debug project | 90 | 2024-04 |
| [kknifer7/CatVodSpider-PC](https://github.com/kknifer7/CatVodSpider-PC) | CatVod / TVBox spider template for PC clients | 56 | 2025-11 |
| [feg545/maccms10-tvbox-api](https://github.com/feg545/maccms10-tvbox-api) | MacCMS v10 → TVBox API bridge | 49 | 2024-08 |
| [hjdhnx/drpy-node-house](https://github.com/hjdhnx/drpy-node-house) | drpyS (drpy-node) source house | 25 | 2026-04 |
| [hjdhnx/drpy3](https://github.com/hjdhnx/drpy3) | drpy3: next-gen source rule engine | 24 | 2026-10 |
| [hjdhnx/drpy-plugin](https://github.com/hjdhnx/drpy-plugin) | drpyS plugins (cross-platform Go binaries) | 20 | 2026-10 |
| [litan1016/spider-craft](https://github.com/litan1016/spider-craft) | Source-dev toolkit: TVBox / T4 / drpy / WebHome | 16 | 2026-09 |

## Tools

| Project | Description | ⭐ | Last push |
|---|---|---|---|
| [power721/alist-tvbox](https://github.com/power721/alist-tvbox) | AList proxy for TVBox: play cloud-drive content (xiaoya) | 3.2k | 2026-11 |
| [wukongdaily/tvhelper-docker](https://github.com/wukongdaily/tvhelper-docker) | Docker-based ADB installer for TV boxes (PC / NAS) | 1.1k | 2026-03 |
| [hl128k/tvbox](https://github.com/hl128k/tvbox) | Interface domain replacement tool | 820 | 2026-10 |
| [wangrongding/tv-fresh](https://github.com/wangrongding/tv-fresh) | Xiaomi TV: remove ads & bloat, swap launcher, install 影视仓 (no root, reversible) | 773 | 2026-10 |
| [fish2018/tvbox](https://github.com/fish2018/tvbox) | Self-host interfaces: mirror json/jar into your own repo | 327 | 2025-04 |
| [drizzle888/CatVodTVJsonEditor](https://github.com/drizzle888/CatVodTVJsonEditor) | CatVod TV config editor (early) | 19 | 2021-12 |
| [outlook84/openlist-tvbox-gateway](https://github.com/outlook84/openlist-tvbox-gateway) | OpenList / AList / WebDAV gateway for TVBox | 12 | 2026-09 |
| [eastar23/tvbox-manager](https://github.com/eastar23/tvbox-manager) | Aggregate interfaces into a multi-repo json + link | 9 | 2026-04 |
| [hnlyzxf/tvbox-api-jm](https://github.com/hnlyzxf/tvbox-api-jm) | TVBox interface decryption | 3 | 2026-07 |
| [JinC-Lab/TVBox-Editor](https://github.com/JinC-Lab/TVBox-Editor) | TVBox interface editor | 2 | 2026-04 |

Online tools (in Chinese):

- [肥猫 interface decrypter](http://xn--z7x900a.net/tool) (`肥猫.net/tool`): decrypts a config from its URL or pasted ciphertext; also encrypts and downloads the JAR / local pack.
- [饭太硬 encrypted-interface parser](https://fty.888484.xyz/jm/): extracts encrypted config interfaces (same domain as the "饭太硬备用" interface above).
- [秋水网 TVBox decrypter](https://www.qiushui.vip/gj/jiemi/): online config decryption.
- [TVBox config editor](https://z.qiqiv.cn/): edits configs in visual or source mode and can convert a config into an image.
- [M3U list converter](https://sankei.mo/z.html): converts live sources between TXT and M3U locally in the browser.
- [gh-proxy.com](https://gh-proxy.com/): GitHub file proxy that speeds up raw configs and release downloads. It is a third-party service, so avoid it for sensitive files.

## Community

- [TVBoxOSC channel](https://t.me/TVBoxOSC) (Telegram): release channel for automated TVBox builds.
- [FongMi discussion group](https://t.me/fongmi_official) (Telegram): official FongMi 影视 group.
- [WebHomeTV](https://t.me/webhtv) (Telegram): WebHomeTV releases and discussion.
- [小没用啊](https://space.bilibili.com/503201096/upload/video) (Bilibili): videos about TV box apps and interfaces.
- [鸭先知&酷啦鱼Ⅰ群](https://qun.qq.com/universal-share/share?ac=1&authKey=7jCQkiAJ1wMBSSASkkAfi7zwCXApT6b2I9KE9UaWpdGkJVYon3YdZ%2B%2B34d7L3cDC&busi_data=eyJncm91cENvZGUiOiI4NTg2Njk1MDQiLCJ0b2tlbiI6InFzV2pWblNjbmgySE84clc5ZGJJWk04T1J5cnp2Ky9nekhlTVc2WnF3d0lQa2pnUkZQaDRVcFpad2FSQ3lzL1UiLCJ1aW4iOiI5NzY2MzY1NSJ9&data=eELPiRTp9gJ3iMA5qJSNZdChqG7tJcQeRjgpEQXlbuKRTw5VtXm2uiZmKEXIwXMWhq7J1-c07LWGR_3Cf9fkKA&svctype=4&tempid=h5_group_info) (QQ group 858669504): chat group for TV box apps and interfaces.
- [zyfun group](https://t.me/+IOovrYLP7gYwYmNl) (Telegram): the chat group linked from the zyfun (formerly ZyPlayer) README.
- [Enshan forum: smart TV and set-top box board](https://www.right.com.cn/forum/forum-281-1.html) (恩山无线论坛): flashing, apps and live sources for TV boxes.
- [ZNDS](https://www.znds.com/) (智能电视网): long-running smart TV and set-top box forum.

## Related Awesome Lists

| Project | Description | ⭐ | Last push |
|---|---|---|---|
| [youhunwl/TVAPP](https://github.com/youhunwl/TVAPP) | Android TV box app collection (video, live, karaoke, tools…) · [Website](https://app.iyouhun.com) | 28.2k | 2026-11 |
| [laoma528/awesome-zhuiju-free](https://github.com/laoma528/awesome-zhuiju-free) | Free ad-free streaming guide (incl. TVBox shells/configs/IPTV) · [Website](https://zhuiju.me) | 15.4k | 2026-11 |
| [iptv-org/awesome-iptv](https://github.com/iptv-org/awesome-iptv) | Curated list of IPTV resources | 12.9k | 2026-11 |

## Sources and Credits

- Resources were collected from public websites, GitHub and community shares; every website, tutorial and tool was opened and verified on 2026-11-12.
- Interface statuses were spot-checked by script on 2026-11-12 (User-Agent `okhttp/3.15`; failures re-checked using DNS over HTTPS); GitHub stars and last-push dates were fetched from the GitHub API on the same day.
- Thanks to all open-source authors, interface maintainers and curators.

## Contributing

Issues and pull requests are welcome:

1. Each entry needs a name, a link and a one-line description in the right category;
2. Make sure the link works before submitting, and mark dead links as such;
3. No cracked / ad-removed modified APKs and no links that directly distribute pirated content;
4. Please keep the Chinese and English READMEs in sync.

## License

[CC0 1.0](LICENSE): to the extent possible under law, the authors have waived all copyright and related rights to this list. Third-party content behind the links belongs to its respective owners.
