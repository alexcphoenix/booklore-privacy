# BookLore 隐私政策 / Privacy Policy

BookLore 阅读器（iOS / iPadOS）的隐私政策页面。

**App 不收集任何数据** —— 没有账号体系、没有分析统计、没有广告、没有第三方 SDK。
App 只连接用户自己填写的 BookLore 服务器地址。

## 页面

`index.html` 是全部内容，单文件、无外部依赖：

- 不加载任何 CDN 字体、脚本或样式表 —— 一个隐私政策页面去引用外部资源是自相矛盾的；
- 不含任何统计或追踪脚本；
- 自适应浅色 / 深色模式，手机与桌面都可读；
- 中文为主，附英文全文（App Store 面向全球审核）。

## 这份政策与代码的一致性

内容不是照模板写的，是**按 App 里已经声明的隐私清单**写的：

- `App/PrivacyInfo.xcprivacy`：`NSPrivacyCollectedDataTypes` 为空数组、
  `NSPrivacyTracking = false`、无追踪域；只声明了两项 required-reason API
  （`UserDefaults` 的 `CA92.1` 与 `FileTimestamp` 的 `C617.1`），且都只作用于 App 自己容器内的数据。
- `App/Info.plist`：**没有任何 `NS*UsageDescription`** —— 所以文中「不申请相机 / 麦克风 / 定位 /
  通讯录 / 健康权限」是可以核对的，不是一句口号。
- 凭据（密码与令牌）走系统钥匙串（`Keychain.swift`），不落普通文件。

改动 App 的数据行为时，**这份政策要跟着改**，否则它就从「说明」变成了「不实陈述」。

## 本地预览

```sh
open index.html
```

## 发布

托管在 GitHub Pages：Settings → Pages → Source 选 `main` 分支的根目录。
