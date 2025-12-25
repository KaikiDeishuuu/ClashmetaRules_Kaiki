# ClashmetaRules_Kaiki

个人 Clash Meta 自定义规则集

## 规则集列表

| 规则集 | 说明 | 引用地址 |
|--------|------|----------|
| custom_direct.yaml | 直连规则（学术、邮件、香港银行、微软等） | [链接](https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_direct.yaml) |
| custom_proxy.yaml | 代理规则（GitHub、AI、开发工具、加密货币等） | [链接](https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_proxy.yaml) |
| custom_google.yaml | Google/YouTube 规则 | [链接](https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_google.yaml) |
| custom_telegram.yaml | Telegram 规则 | [链接](https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_telegram.yaml) |
| custom_germany.yaml | 德国服务规则（N26、PayPal等） | [链接](https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_germany.yaml) |

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

  custom_google:
    type: http
    behavior: domain
    url: https://raw.githubusercontent.com/KaikiDeishuuu/ClashmetaRules_Kaiki/main/custom_google.yaml
    path: ./ruleset/custom_google.yaml
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
```

在 `rules` 中引用：

```yaml
rules:
  - RULE-SET,custom_telegram,TG
  - RULE-SET,custom_google,Google
  - RULE-SET,custom_germany,德国服务
  - RULE-SET,custom_proxy,全球代理
  - RULE-SET,custom_direct,DIRECT
  # ... 其他规则
```
