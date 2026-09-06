---
layout: default
title: NaviCast 隐私政策
permalink: /privacy-policy-zh.html
lang: zh-CN
---

# 隐私政策 — NaviCast

**应用名称**：NaviCast
**应用 ID**：`com.gioitv.navicast`
**开发者**：gioitv（gioitv86@gmail.com）
**生效日期**：2026-05-08
**最后更新**：2026-09-06

---

## 1. 摘要

NaviCast 是一款 Android 配套应用，将逐步导航图标从您的手机转发到已配对的智能手表。目前支持华为手表，通过 Huawei Health 和 Huawei Wear Engine 实现。

**通知内容 — NaviCast 读取的转弯文字、地址、预计到达时间和地点名称 — 在任何版本下都不会被收集、存储或传输出您的设备。** 它在本地处理后即被丢弃。

唯一会离开手机的是**位置**，且仅在 Ultimate 版开启实时地图后：坐标会发送至开源地图服务，以换取地图瓦片、路线和地点名称。参见第 2b 节。

如果您只读一段，请读这一段：
- ❌ 没有用户账户，无需登录。
- ❌ 没有数据分析，没有跟踪，没有广告 SDK。
- ❌ 通知内容（文字、地址、预计到达时间、地名）**绝不会**被上传、存储到服务器或与第三方共享。
- ❌ 不访问通讯录、麦克风、摄像头、短信或存储。
- ⚠️ **位置** — 仅限 Ultimate 版，且仅在您开启实时地图后。参见第 2b 节。
- ✅ 仅在您的设备上读取 Google Maps 通知，将其转换为适合手表的通知，然后交给已配对的手表 — 目前通过 Huawei Health 或 Huawei Wear Engine。
- 💳 NaviCast 免费试用。试用期后，通过 **Google Play 结算**进行一次性内购即可永久解锁 — NaviCast 绝不会看到、处理或存储您的支付卡信息，购买也不与我们持有的任何账户关联（我们没有任何账户）。

---

## 2. 我们收集的数据

**无。** NaviCast 不收集、传输或持久化任何个人数据。具体来说：

| 数据类型 | 是否收集？ | 备注 |
|---|---|---|
| 个人标识符（姓名、邮箱、电话、账户 ID） | ❌ 否 | 应用没有账户系统 |
| 位置 | ⚠️ 是 — 仅限 Ultimate 版 | 用于实时地图和独立导航；坐标会发送至开源地图服务。参见第 2b 节 |
| 通讯录、短信、通话记录 | ❌ 否 | **不**请求这些权限 |
| 通知内容（Google Maps 转向文字、地址） | ⚠️ 仅在设备上读取 | 仅用于在本地通知上渲染图标 + 距离标签。不持久化、不记录、不传输。 |
| 设备标识符（IMEI、广告 ID） | ❌ 否 | 应用**不**读取设备 ID |
| 崩溃报告、分析、诊断 | ❌ 否 | NaviCast 不包含 Firebase、Crashlytics、Sentry 或任何分析 SDK |
| 文件、照片、媒体 | ❌ 否 | **不**请求存储权限 |
| 支付 / 银行卡信息 | ❌ 否 | 一次性购买由 **Google Play 结算**处理。NaviCast 绝不会收到您的卡号、账单地址或任何支付工具数据。 |
| 购买状态 | ⚠️ 仅在设备上 | 购买后，NaviCast 在本地存储一个「已解锁」标志并向 Google Play 查询以确认您的权益。该标志不是个人数据，也不会传输给我们（我们没有服务器）。 |

**应用设置**（手表型号预设、距离单位、语言、主题、振动开关、引导完成标志）通过 Android Jetpack DataStore 存储在应用的私有存储区域中。这些设置：
- 永远不会离开您的设备。
- 在应用卸载时被清除。
- 不包含个人数据 — 仅是您的 UI 偏好。

---


## 2b. 位置 — 仅限 Ultimate 版

**Ultimate** 版提供实时地图和独立导航模式。**只有在您开启该功能时**，NaviCast 才会请求精确位置权限
（`ACCESS_FINE_LOCATION`）。**Standard** 版和 **Pro** 版从不请求位置权限。

位置用于：
- 将地图对准您所在的位置，并渲染发送到手表的地图图像；
- 计算路线以及到下一个转弯处的距离；
- 在您搜索或分享地址时，把坐标转换成地点名称。

**您的坐标会发送到以下开源地图服务**，仅用于上述用途，且仅在您正在导航时：

| 服务 | 接收内容 | 用途 |
|---|---|---|
| `api.maptiler.com` 或 `tiles.openfreemap.org` | 您周围的地图范围 | 地图瓦片 |
| `valhalla1.openstreetmap.de` | 起点和终点 | 路线计算 |
| `photon.komoot.io` | 坐标或搜索关键词 | 地点搜索与逆地理编码 |

NaviCast **没有自己的服务器**，除您的设备外**不在任何地方保存位置历史**，也**从不将位置用于广告、
分析或用户画像**。NaviCast **不**请求后台位置权限（`ACCESS_BACKGROUND_LOCATION`）。

`location` 类型的前台服务仅在您按下**开始**后运行，并在您按下**停止**时立即结束。关闭地图功能，或
在 Android 设置中撤销位置权限，即可完全终止上述行为。


## 3. 我们请求的权限

NaviCast **仅**请求执行其功能所需的最低权限：

| 权限 | 用途 |
|---|---|
| `BIND_NOTIFICATION_LISTENER_SERVICE` | 在您的手机上读取 Google Maps 导航通知。这是知道何时即将出现转向操作的**唯一**方式。系统通过设置中的「通知访问」开关强制执行此权限 — 您控制 NaviCast 何时可以读取通知。 |
| `POST_NOTIFICATIONS`（Android 13+） | 创建包含转向图标的本地通知；手表的配套应用（目前为 Huawei Health）会将其转发到您的手表。 |
| `FOREGROUND_SERVICE` + `FOREGROUND_SERVICE_SPECIAL_USE` | 在导航期间保持我们的通知监听器运行（否则 Android 在某些设备上会在几分钟后将其终止）。 |
| `com.android.vending.BILLING` | 通过 Google Play 结算提供试用期后解锁应用的一次性内购。NaviCast 不处理任何支付数据。 |

我们**不**请求：通讯录、短信、麦克风、摄像头、存储、蓝牙、电话状态、「查询所有应用包」或**后台位置**。

我们**会**请求**精确位置** — 仅限 Ultimate 版，且仅在您开启实时地图后。参见第 2b 节。

您可以随时撤销 `BIND_NOTIFICATION_LISTENER_SERVICE` 权限：
**设置 → 应用 → 特殊访问 → 通知访问 → 关闭 NaviCast。**

关闭后，NaviCast 无法读取任何通知，包括 Google Maps。转发立即停止。

---

## 4. 第三方服务

NaviCast 使用 Google Play 结算处理购买，并且 — 仅在 Ultimate 版 — 使用开源地图服务来实现实时地图。具体来说：
- ❌ 没有 Firebase、Google Analytics 或除标准 Android 系统服务和结算之外的任何 Google Play 服务 SDK。
- ❌ 没有 Crashlytics、Sentry、Bugsnag 或其他崩溃报告工具。
- ❌ 没有广告 SDK。
- ❌ 没有社交登录。
- ✅ **Google Play 结算** — 仅用于处理试用期后解锁应用的一次性内购。
- ✅ **华为 IAP** — 与 Google Play 结算作用相同，适用于从 AppGallery 安装的版本。
- ✅ **MapTiler / OpenFreeMap、Valhalla、Photon** — 仅限 Ultimate 版，用于地图瓦片、路线计算和地点搜索。导航期间这些服务会接收您的坐标。参见第 2b 节。

**Google Play 结算。** 当您选择购买时，NaviCast 会将您转交给 Google Play 商店应用，由其完全在其一侧收集和处理您的付款。NaviCast 仅收到确认解锁的购买令牌 / 权益状态 — 绝不会收到您的卡号、账单地址或任何支付工具。Google 对该支付数据的处理受 **Google 隐私政策**（https://policies.google.com/privacy）约束，而非我们。

NaviCast 仅以间接方式与 **Huawei Health** 交互：它发布一个普通的 Android 通知，Huawei Health（您单独安装和配置）以读取任何其他通知的相同方式读取它。我们不直接使用 Huawei Health 的 API。

---

## 5. 数据共享

除下列两种情况外，我们**不与任何人共享数据**，也没有其他内容离开您的设备。**在任何版本下，通知内容都绝不会被传输到任何地方。**

具体来说：
- 我们不出售您的数据。
- 我们不与广告商共享。
- 我们不与分析提供商共享。
- 我们不与执法机构共享（我们没有数据可提供）。

第一个例外是 **Ultimate 版的位置**：导航期间，您的坐标会发送到第 2b 节所列的开源地图服务，以便返回地图瓦片、路线和地点名称。这些服务由第三方运营，适用其各自的隐私政策。我们只发送该请求所需的坐标和搜索关键词 — 不含任何标识符、账号或通知内容。

第二个例外是**支付处理**：如果您进行购买，付款将直接在您与 **Google Play** 之间处理，受 Google 自己的隐私政策约束。NaviCast 既不接收也不转发该支付数据 — 我们只知道解锁是否成功。

---

## 6. 儿童隐私

NaviCast 不面向 13 岁以下儿童。应用不会有意从任何人（包括儿童）那里收集数据。由于没有收集任何内容，因此没有任何关于儿童的内容需要存储、删除或报告。

---

## 7. 您的权利

由于 NaviCast 不收集任何数据，因此没有数据可访问、删除或导出。然而：

- **要阻止应用读取通知**：撤销通知访问权限（设置 → 应用 → 特殊访问 → 通知访问 → NaviCast → 关闭）。
- **要完全停止应用**：卸载它。所有本地设置都将被清除。
- **要请求信息**：联系开发者（请参阅下面的 §10）。我们将在 30 天内回复。

如果您居住在欧盟/英国（GDPR/UK DPA）、欧洲经济区、加利福尼亚州（CCPA）或类似管辖区，您访问/更正/删除个人数据的权利在默认情况下得以保留 — 因为根本没有处理任何个人数据。

中华人民共和国《个人信息保护法》（PIPL）赋予您查询、更正、删除个人信息及撤回同意的权利。由于 NaviCast 不收集任何个人信息，因此没有可处理的请求；但您可以通过下方 §10 联系我们以获得书面确认。

---

## 8. 安全

NaviCast 遵循防御性安全实践：
- 所有处理**仅在设备上**进行。没有服务器。
- 通知内容在易失性内存（RAM）中保留一次导航会话的持续时间，然后被释放。
- 通知内容不会在发布版本中记录（通过源代码审计 + ProGuard 规则验证）。
- 已签名的发布 APK 通过自动化 CI 流程构建；签名密钥永远不会离开开发者的安全环境。
- 源代码为闭源，并在每次发布前经过审查。

---

## 9. 政策变更

如果我们更改此政策，我们将：
1. 更新顶部的「最后更新」日期。
2. 在应用的发布说明（应用商店）中注明该变更。
3. 如果变更是重大的（例如，我们曾经开始收集任何数据 — 我们没有这样做的计划），我们将在变更生效之前要求用户明确同意。

您可以在以下网址查看当前版本：`https://gioiktvt.github.io/navicast-legal/privacy-policy-zh.html`（简体中文）、`https://gioiktvt.github.io/navicast-legal/privacy-policy.html`（English）或 `https://gioiktvt.github.io/navicast-legal/privacy-policy-vi.html`（Tiếng Việt）。

---

## 10. 联系方式

如对本隐私政策有疑问、请求或顾虑：

- **邮箱**：gioitv86@gmail.com

请使用英语、越南语或中文。

---

## 11. 商标声明

「Google Maps」和 Google Maps 标志是 Google LLC 的商标。
「Huawei」、「Huawei Health」、「Huawei Watch」、「Huawei Band」、「Huawei Watch GT」、「Huawei Watch Fit」是华为技术有限公司的商标。

NaviCast 是**独立的第三方配套应用**。它**不隶属于、不被 Google 或华为认可或赞助**。NaviCast 不使用这些公司的 API（除了读取公开的 Android 通知 — 任何具有通知访问权限的用户安装的应用都可以做到）。

---

## 12. 第三方资源

某些转向图标（转向箭头、环岛、匝道、岔路）源自 **Google Material Symbols** 图标集，根据 [Apache License 2.0](https://github.com/google/material-design-icons/blob/master/LICENSE) 分发。图标集按原样使用（缩放以适应手表显示，未修改路径数据）。Material Symbols 版权归 © Google LLC 和 Material Design 作者所有。

NaviCast 在其品牌、营销或商店展示的任何地方均不使用 Google 商标（Google 名称或标志）。

---

*本政策以简体中文编写。其他语言版本：[English](privacy-policy-en.md)、[Tiếng Việt](privacy-policy-vi.md)。所有版本具有同等法律效力；如有分歧，越南语版本适用于越南用户，简体中文版本适用于中国大陆用户，英语版本适用于其他地区。*
