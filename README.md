# ClashmetaRules_Kaiki

个人 Clash Meta 自定义规则集

## 规则集列表

| 规则集 | 说明 | 引用地址 |
|--------|------|----------|
| custom_direct.yaml | 直连规则（学术、国内服务、香港银行等；微软流量已移出） | [链接](https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_direct.yaml) |
| custom_direct_ip.yaml | 本机、私有网络、运营商级 NAT 与南科大校园 IPv6 地址直连 | [链接](https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_direct_ip.yaml) |
| custom_proxy.yaml | 代理规则（GitHub、AI、微软、开发工具、加密货币等） | [链接](https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_proxy.yaml) |
| custom_ai.yaml | AI 服务规则（OpenAI、Grok、Perplexity、Mistral 等） | [链接](https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_ai.yaml) |
| custom_claude.yaml | Claude / Anthropic 专属规则（含网页支付依赖） | [链接](https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_claude.yaml) |
| custom_apple.yaml | Apple 规则（iCloud、App Store、Apple Music 等） | [链接](https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_apple.yaml) |
| custom_google.yaml | Google/YouTube 规则 | [链接](https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_google.yaml) |
| custom_meta.yaml | Meta 系服务规则（Facebook、Instagram、Threads、Messenger、WhatsApp、Meta Quest 等） | [链接](https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_meta.yaml) |
| custom_telegram.yaml | Telegram 规则 | [链接](https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_telegram.yaml) |
| custom_tiktok.yaml | TikTok 规则 | [链接](https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_tiktok.yaml) |
| custom_streaming.yaml | 流媒体通用规则（Netflix/Disney+/Spotify/Max/PrimeVideo/Hulu 等；YouTube 走 custom_google） | [链接](https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_streaming.yaml) |
| custom_germany.yaml | 德国服务规则（N26、PayPal等） | [链接](https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_germany.yaml) |
| custom_reject.yaml | 拦截规则（当前仅保留无效 WPAD 等规则；微软流量改走代理） | [链接](https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_reject.yaml) |

## 使用方法

在 Clash Meta 配置文件的 `rule-providers` 中添加：

```yaml
rule-providers:
  custom_direct:
    type: http
    behavior: domain
    url: https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_direct.yaml
    path: ./ruleset/custom_direct.yaml
    interval: 86400

  custom_direct_ip:
    type: http
    behavior: ipcidr
    url: https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_direct_ip.yaml
    path: ./ruleset/custom_direct_ip.yaml
    interval: 86400

  custom_proxy:
    type: http
    behavior: domain
    url: https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_proxy.yaml
    path: ./ruleset/custom_proxy.yaml
    interval: 86400

  custom_ai:
    type: http
    behavior: domain
    url: https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_ai.yaml
    path: ./ruleset/custom_ai.yaml
    interval: 86400

  custom_claude:
    type: http
    behavior: domain
    url: https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_claude.yaml
    path: ./ruleset/custom_claude.yaml
    interval: 86400

  custom_apple:
    type: http
    behavior: domain
    url: https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_apple.yaml
    path: ./ruleset/custom_apple.yaml
    interval: 86400

  custom_google:
    type: http
    behavior: domain
    url: https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_google.yaml
    path: ./ruleset/custom_google.yaml
    interval: 86400

  custom_meta:
    type: http
    behavior: domain
    url: https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_meta.yaml
    path: ./ruleset/custom_meta.yaml
    interval: 86400

  custom_tiktok:
    type: http
    behavior: domain
    url: https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_tiktok.yaml
    path: ./ruleset/custom_tiktok.yaml
    interval: 86400

  custom_streaming:
    type: http
    behavior: domain
    url: https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_streaming.yaml
    path: ./ruleset/custom_streaming.yaml
    interval: 86400

  custom_telegram:
    type: http
    behavior: domain
    url: https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_telegram.yaml
    path: ./ruleset/custom_telegram.yaml
    interval: 86400

  custom_germany:
    type: http
    behavior: domain
    url: https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_germany.yaml
    path: ./ruleset/custom_germany.yaml
    interval: 86400

  custom_reject:
    type: http
    behavior: domain
    url: https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_reject.yaml
    path: ./ruleset/custom_reject.yaml
    interval: 86400
```

> `custom_claude` 包含 Stripe、Stripe CDN 与 hCaptcha 等网页结账依赖。这些是共享服务，因此其他使用它们的网站也会命中 `Claude` 策略组；如不需要网页端支付，可从该规则集中移除对应条目。

> `custom_meta` 与 `custom_ai` 都包含 Meta AI 域名。若希望 Meta AI 使用 `Meta` 策略组，请像下方示例一样，将 `custom_meta` 放在 `custom_ai` 前面。

> Microsoft、Windows Update、Office、OneDrive、Outlook、Bing、Azure、Teams、Skype、Visual Studio 和 Xbox 相关域名统一命中 `custom_proxy`，通过代理出站；它们不再出现在 `custom_direct` 或 `custom_reject` 中。

在 `rules` 中引用：

```yaml
rules:
  - RULE-SET,custom_reject,REJECT
  - RULE-SET,custom_direct_ip,DIRECT,no-resolve
  - RULE-SET,custom_telegram,TG
  - RULE-SET,custom_apple,全球代理
  - RULE-SET,custom_google,Google
  - RULE-SET,custom_meta,Meta
  - RULE-SET,custom_tiktok,全球代理
  - RULE-SET,custom_streaming,流媒体
  - RULE-SET,custom_germany,德国服务
  - RULE-SET,custom_claude,Claude
  - RULE-SET,custom_ai,全球代理
  - RULE-SET,custom_proxy,全球代理
  - RULE-SET,custom_direct,DIRECT
  # ... 其他规则
```

### 跳过私网地址嗅探

将以下网段合并到主配置的 `sniffer.skip-dst-address` 中，可避免 Mihomo 对无 HTTP 数据的内网连接反复嗅探并输出 `may not have any sent data` 日志：

```yaml
sniffer:
  skip-dst-address:
    - 10.0.0.0/8
    - 100.64.0.0/10
    - 127.0.0.0/8
    - 169.254.0.0/16
    - 172.16.0.0/12
    - 192.168.0.0/16
    - ::1/128
    - fc00::/7
    - fe80::/10
    - 2001:da8:201d::/48
```

根据[南科手册的校园网络说明](https://sustech.online/service/network/)，南科大 IPv4 校园网段 `10.16.0.0/13` 和 `172.18.0.0/16` 已分别包含在上述 `10.0.0.0/8` 和 `172.16.0.0/12` 中；校园 IPv6 前缀 `2001:da8:201d::/48` 则单独列出。

`wpad.sustech.edu.cn` 已收录在 `custom_reject` 中，因此需保持 `custom_reject` 位于 `custom_direct` 之前，避免它被 `+.edu.cn` 提前命中并尝试直连 `255.255.255.255`。
