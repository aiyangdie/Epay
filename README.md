# 彩虹易支付系统

**彩虹易支付系统** 由郑州追梦网络科技有限公司开发，是一款开源的免签约支付产品，能够帮助开发者一站式接入支付宝、微信、财付通、QQ钱包等多种支付方式，实现高效的支付集成。

---

## 项目信息

| 项目 | 信息 |
|------|------|
| **版本** | 3097 |
| **更新时间** | 2026/04/29 |
| **安全状态** | 已清理可疑插件 ✅ |
| **PHP要求** | PHP 7.4+ |
| **数据库** | MySQL 5.6+ |

---

## 功能特色

- **多渠道支付集成**：支持支付宝、微信、财付通、QQ钱包、微信WAP、银联、抖音等多种支付方式
- **便捷的支付解决方案**：简化支付流程，支持快速集成和上线，提供完整的 API 接口
- **后台管理和数据统计**：提供支付统计、代付统计、利润分析等多种后台管理功能
- **安全可靠**：采用 RSA/MD5 公私钥验证，支持 TOTP 二次验证、风控检测和黑名单管理
- **插件扩展**：支持丰富的支付插件，可根据需求灵活扩展
- **移动端优化**：全新的手机版支付页面，支持各种移动端支付场景
- **分账功能**：支持微信、支付宝分账
- **代付功能**：支持支付宝、微信、QQ、银行卡转账

---

## 支付插件 (63个)

### 官方支持
- `alipay` - 支付宝
- `wxpay` - 微信支付
- `qqpay` - QQ钱包
- `bank` - 银行卡
- `jdpay` - 京东支付
- `paypal` - PayPal

### 第三方插件
| 插件 | 说明 |
|------|------|
| `bepusdt` | USDT (TRC20) 收款 ⭐ |
| `douyinpay` | 抖音支付 |
| `alipaycode` | 支付宝当面付 |
| `alipayd` | 支付宝担保交易 |
| `alipayg` | 支付宝国际版 |
| `alipayhk` | 支付宝香港 |
| `alipayrp` | 支付宝转账红包 |
| `alipaysl` | 支付宝扫码领红包 |
| `allinpay` | 通联支付 |
| `baofu` | 宝付支付 |
| `chinaums` | 银联商务 |
| `dinpay` | 智付 |
| `duolabao` | 多拉宝 |
| `easypay` | 易宝支付 |
| `fubei` | 富友支付 |
| `fuiou` / `fuiou2` / `fuiou3` | 富友支付 |
| `heepay` | 汇付天下 |
| `helipay` | 合利宝 |
| `hlpay` | 华利支付 |
| `hnapay` | 华南支付 |
| `huifu` | 汇付 |
| `huolian` | 火链支付 |
| `stripe` | Stripe |
| `swetpay` | SWET支付 |
| `tftpay` | 天府支付 |
| `xorpay` | XORPay |
| `yeepay` | 易宝支付 |
| `ysepay` | 银盛支付 |
| `vmq` | VMQ支付 |

---

## 安装要求

### 环境要求
- **PHP**: 7.4 或更高版本
- **PHP扩展**: curl, gd, mbstring, openssl, pdo_mysql, json, zip
- **数据库**: MySQL 5.6 或更高版本
- **Web服务器**: Nginx / Apache / IIS

### 推荐环境
- **操作系统**: Linux (Ubuntu/CentOS/Debian)
- **Web服务器**: Nginx + PHP-FPM
- **PHP版本**: 8.0 或 8.1

### 必需PHP扩展
```
curl    - 用于HTTP请求
gd      - 图形处理
mbstring - 多字节字符串
openssl  - 加密/签名
pdo_mysql - 数据库连接
json    - JSON处理
zip     - 压缩处理
```

---

## 安装教程

### 1. 下载源码
```bash
git clone https://github.com/aiyangdie/Epay.git
```

### 2. 上传源码
将源码上传到网站根目录

### 3. 设置权限
```bash
chmod -R 755 ./
chmod -R 777 ./cache/
chmod -R 777 ./logs/
```

### 4. 创建数据库
```sql
CREATE DATABASE epay DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci;
```

### 5. 访问安装向导
打开浏览器访问 `http://你的域名/install/` 完成安装

---

## API 接口

### 接口地址
```
https://你的域名/api.php
```

### 主要接口

| 接口 | 说明 |
|------|------|
| `?act=query` | 商户信息查询 |
| `?act=settle` | 结算记录查询 |
| `?act=order` | 订单查询 |
| `?act=orders` | 订单列表查询 |
| `?act=refund` | 订单退款 |

### 支付接口
```
?act=pay&pid=商户ID&key=商户密钥&out_trade_no=订单号&money=金额&notify_url=回调地址&return_url=返回地址&type=支付方式
```

---

## 安全设置

### 二次验证
- 后台登录支持 TOTP 二次验证（Google Authenticator）
- 建议开启：系统设置 → 安全设置 → 开启二次验证

### IP白名单
- 可设置后台登录IP白名单
- 可设置API调用IP白名单

### 风控配置
- 支持设置支付金额限制
- 支持设置订单成功率检测
- 支持IP黑名单管理

---

## 常见问题

### Q: 商户注册提示"注册收款商户ID不存在"
A: 这是已知的Bug，建议在后台手动创建商户

### Q: 如何配置支付宝当面付
A:
1. 在支付宝开放平台创建应用
2. 签约当面付产品
3. 在后台支付通道配置 appid、密钥、商户号

### Q: 如何配置微信支付
A:
1. 在微信支付商户平台申请商户号
2. 配置API密钥和证书
3. 在后台支付通道配置相关信息

### Q: USDT支付如何配置
A:
1. 安装 bepusdt 插件
2. 配置 TRON 钱包地址
3. 设置 USDT 汇率

---

## 更新日志

### 2026/04/29
- ✅ 安全修复：删除可疑 jfyui 插件

### 2026/02/28
- 新增 H5 跳转微信小程序客服支付

### 2026/02/23
- 新增抖音支付
- 部分间连支付分账规则支持选择实时和延迟分账
- 新增发起支付地区屏蔽设置

### 2026/01/28
- 后台登录增加 TOTP 二次验证
- 新增校验扫码 IP 所在地与下单 IP 所在地是否一致功能
- 非官方微信支付插件可开启扫码支付前快捷登录
- 增加获取微信小程序用户标识功能
- 用户组增加更多配置项
- 中转代理增加代理 API 的方式
- 优化随机增减金额逻辑

### 2025/11/10
- 后台新增转账付款统计
- 付款页面新增最近付款人按钮
- 支持开启分账失败的订单24小时后重试
- 支付通道支持设置开放时间段
- 新增订单小票打印功能
- API接口增加身份证/姓名/年龄限制参数

### 2025/08/26
- 增加渠道交易单号查询
- 增加检测单个支付账号订单支付速度自动封禁账号
- 公共静态资源CDN可选择本地
- 支付宝身份认证支持海外身份证

---

## 推荐插件

### Bepusdt (USDT收款) ⭐
适用于彩虹易支付系统的 USDT（TRC20）收款插件，收到的货币直接转入商户钱包，不经过任何第三方。

**插件开源地址**：[https://github.com/v03413/bepusdt](https://github.com/v03413/bepusdt)

### BEpusdt (新版) ⭐⭐
Go语言开发的 USDT 收款网关，性能更好，支持多链（TRON/Ethereum/BSC/Polygon），无需 MySQL/Redis。

**项目地址**：[https://github.com/v03413/BEpusdt](https://github.com/v03413/BEpusdt)

---

## 官方信息

- **开发公司**: 郑州追梦网络科技有限公司
- **官方网站**: https://pay.v8jisu.cn
- **官方GitHub**: https://github.com/maajiko/Epay

---

## 免责声明

本项目仅供学习交流使用，请勿用于商业违规用途。使用本项目造成的任何法律后果由使用者自行承担。

---

## 许可证

MIT License

---

## 交流群

有问题可以在 GitHub Issues 中提交，或加入官方交流群讨论。
