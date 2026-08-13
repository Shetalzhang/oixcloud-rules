# oixcloud-rules

为 oixcloud (Anywhere) iOS 客户端准备的规则集（`.arrs` 格式）。

来源：https://github.com/iurd/OpenClash_Rules （由 Clash 格式转换）

## 规则集

| 文件 | 内容 | 初始行为 |
|------|------|----------|
| `Custom_Direct.arrs` | 国内冷门域名 + 直连域名/IP（GitHub 反代、Docker 反代、DDNS、Emby 等） | 1 = Direct |
| `Custom_Proxy.arrs` | 强制走代理的域名/IP（Google 服务、PlayStation STUN 等） | 0 = Default（需手动分配代理） |
| `Steam_CDN.arrs` | Steam 下载 CDN 域名/IP，强制直连 | 1 = Direct |

## 使用

在 oixcloud / Anywhere 的 **Routing Rules** 中添加订阅，填入下方 raw URL（私有仓库需登录或改用带 token 的 URL）。

raw 根路径：`https://raw.githubusercontent.com/Shetalzhang/oixcloud-rules/main/`

- `https://raw.githubusercontent.com/Shetalzhang/oixcloud-rules/main/Custom_Direct.arrs`
- `https://raw.githubusercontent.com/Shetalzhang/oixcloud-rules/main/Custom_Proxy.arrs`
- `https://raw.githubusercontent.com/Shetalzhang/oixcloud-rules/main/Steam_CDN.arrs`

订阅后：
- `Custom_Direct` / `Steam_CDN` 已标记 Direct，无需再改。
- `Custom_Proxy` 初始为 Default（未生效），需在 Routing Rules 里把它分配给代理节点。

## 更新

上游规则每日变化，订阅刷新会整体替换规则，本地分配的动作不会丢失。
