# V2b-theme-Ito (糸)

**V2board 前后分离的极精简主题**

Ito（糸）是一个基于 V2board 的前后端分离静态主题。
设计简洁、轻量，仅保留客户端下载、套餐购买、邀请与个人中心等核心功能，适合对页面功能需求统一、无需过多扩展的场景。  
快速反馈：[@dyaogroup](https://t.me/dyaogroup)  
在线体验：https://v2btheme-ito.vercel.app/

---

## 特性

* 📄 ​**纯 HTML 静态文件**​，无需后端渲染或构建工具
* ⚙️ ​**配置集中管理**​：所有可定制项集中在 `config.js`
* 🌐 ​**前后端分离**​：前端与 V2board 后端通过 API 通信，支持任意静态托管方案


## 快速开始

1. ​**下载或克隆仓库**​：
   ```bash
   git clone https://github.com/yourname/V2b-theme-Ito.git
   ```
2. ​**修改配置**​：
   * 打开 `config.js`，填入你的 V2board 后端 API 地址、站点信息、主题配色等。
3. ​**部署静态文件**​：
   * 将根目录下所有文件上传到你的静态服务器（如 Nginx、Apache 或 GitHub Pages）。
4. ​**访问页面**​：
   * 打开 `https://your-domain.com/index.html` 即可查看个人中心主页，其他页面路径类似。

---

## 配置说明（config.js）

```js
window.settings = {
    // API
    api: "https://v2b.haruka.cloud",
    // 站点名称
    title: 'Demo App',
    // 站点描述
    description: '连接全世界',
    // 站点介绍 
    introduction: '我们是一个追求更可靠、安全、高效且高性价比的互联网接入方案。',
    // Crisp 客服系统网站 ID
    crisp_id: '',
    // 客户端配置
	// apps 内根据需要自行添加修改
	// items 只能修改true/false
    clients: [
        {
            name: "iOS",
            apps: [
                {
                    name: "Shadowrocket",
                    icon: "https://is1-ssl.mzstatic.com/image/thumb/Purple211/v4/be/0e/ec/be0eecda-9042-7bdd-b720-8e89ceb0dcf7/AppIcon-0-0-1x_U007epad-0-1-85-220.png/230x0w.webp",
                    link: "https://apps.apple.com/us/app/shadowrocket/id932747118",
                },
                {
                    name: "Loon",
                    icon: "https://is1-ssl.mzstatic.com/image/thumb/Purple221/v4/13/42/d7/1342d7d8-7cfd-4ef9-8dd7-544027bd5c71/AppIcon-0-0-1x_U007emarketing-0-8-0-85-220.png/230x0w.webp",
                    link: "https://apps.apple.com/us/app/loon/id1373567447",
                },
            ],
            items: {
                Shadowrocket: true,
                Loon: true,
            }
        },
        {
            name: "Android",
            apps: [
                {
                    name: "Clash Meta",
                    icon: "https://clashmeta.org/wp-content/uploads/2023/07/cropped-favicon-50x50.png",
                    link: "https://github.com/MetaCubeX/ClashMetaForAndroid",
                },
                {
                    name: "FlClash",
                    icon: "https://getflclash.net/wp-content/uploads/2024/10/logo-150x150.webp",
                    link: "https://github.com/chen08209/FlClash",
                },
            ],
            items: {
                "Clash Meta": true,
                FlClash: true,
            }
        },
        {
            name: "Windows",
            apps: [
                {
                    name: "Clash Verge",
                    icon: "https://avatars.githubusercontent.com/u/152534467?s=200&v=4",
                    link: "https://github.com/clash-verge-rev/clash-verge-rev",
                },
                {
                    name: "FlClash",
                    icon: "https://getflclash.net/wp-content/uploads/2024/10/logo-150x150.webp",
                    link: "https://github.com/chen08209/FlClash",
                },
            ],
            items: {
                "Clash Verge": true,
                FlClash: true,
            }
        },
        {
            name: "Mac OS",
            apps: [
                {
                    name: "Clash Verge",
                    icon: "https://avatars.githubusercontent.com/u/152534467?s=200&v=4",
                    link: "https://github.com/clash-verge-rev/clash-verge-rev",
                },
                {
                    name: "FlClash",
                    icon: "https://getflclash.net/wp-content/uploads/2024/10/logo-150x150.webp",
                    link: "https://github.com/chen08209/FlClash",
                },
            ],
            items: {
                "Clash Verge": true,
                FlClash: true,
            }
        },
    ],
	// 首页描述
    feature: {
        title: "我们使用最新的技术来提供最佳体验",
        subtitle: "我们致力于提供最可靠、安全、高效且高性价比的互联网接入方案。",
        items: [
            {
                name: "流媒体解锁",
                desc: "我们支持多种流媒体平台的解锁，包括 Netflix、Disney+、Hulu 等，确保您可以随时随地享受高质量的娱乐内容。",
                icon: "",
            },
            {
                name: "AI 平台支持",
                desc: "我们支持多种 AI 平台，包括 OpenAI、Google AI 等，确保您可以使用最新的人工智能技术来提升工作效率和生活质量。",
                icon: "",
            },
            {
                name: "隐私保护",
                desc: "我们重视您的隐私，采用先进的加密技术和严格的隐私政策，确保您的数据安全和匿名性。",
                icon: "",
            },
        ]
    }
}
```

> ​**提示**​：修改完毕后，无需重新构建，静态文件会动态加载最新配置。

---

## 后端支付回调

> ​**若没有正常回调**​：你需要修改后端内容来确保支付完成的回调

服务端目录：`/app/Services`
对应文件：`PaymentService.php`

找到 `'return_url'` 修改 `=>` 后的内容  
修改为：`'return_url' => $_SERVER["HTTP_ORIGIN"] . "/profile",`

---

## Nginx刷新后出现 404

如果你直接刷新子页面（例如 /profile）出现 404，请在复写配置中加上：
```
location / {
    try_files $uri $uri/ $uri.html /index.html;
}
```
