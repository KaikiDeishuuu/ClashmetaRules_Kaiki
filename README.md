# ClashmetaRules_Kaiki

个人 Clash Meta 自定义规则集

## 规则集列表

| 规则集 | 说明 | 引用地址 |
|--------|------|----------|
| custom_direct.yaml | 直连规则（学术、邮件、香港银行、微软等） | [链接](https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_direct.yaml) |
| custom_proxy.yaml | 代理规则（GitHub、AI、开发工具、加密货币等） | [链接](https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_proxy.yaml) |
| custom_ai.yaml | AI 服务规则（OpenAI、Grok、Perplexity、Mistral 等） | [链接](https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_ai.yaml) |
| custom_claude.yaml | Claude / Anthropic 专属规则（含网页支付依赖） | [链接](https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_claude.yaml) |
| custom_apple.yaml | Apple 规则（iCloud、App Store、Apple Music 等） | [链接](https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_apple.yaml) |
| custom_google.yaml | Google/YouTube 规则 | [链接](https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_google.yaml) |
| custom_telegram.yaml | Telegram 规则 | [链接](https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_telegram.yaml) |
| custom_tiktok.yaml | TikTok 规则 | [链接](https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_tiktok.yaml) |
| custom_germany.yaml | 德国服务规则（N26、PayPal等） | [链接](https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_germany.yaml) |
| custom_reject.yaml | 拦截规则（Windows 更新等） | [链接](https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_reject.yaml) |

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

  custom_tiktok:
    type: http
    behavior: domain
    url: https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_tiktok.yaml
    path: ./ruleset/custom_tiktok.yaml
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

在 `rules` 中引用：

```yaml
rules:
  - RULE-SET,custom_reject,REJECT
  - RULE-SET,custom_telegram,TG
  - RULE-SET,custom_apple,全球代理
  - RULE-SET,custom_google,Google
  - RULE-SET,custom_tiktok,全球代理
  - RULE-SET,custom_germany,德国服务
  - RULE-SET,custom_claude,Claude
  - RULE-SET,custom_ai,全球代理
  - RULE-SET,custom_proxy,全球代理
  - RULE-SET,custom_direct,DIRECT
  # ... 其他规则
```
