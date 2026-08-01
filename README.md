AI 新闻日报自动化工作流 / AI News Daily Automation Workflow
基于 n8n 的 AI 新闻自动抓取 → DeepSeek 分析 → 飞书推送 → 多维表格存档
An n8n-based workflow for automated AI news aggregation, analysis, and delivery to Feishu.
📖 项目简介 / Overview
中文版
这是一个基于 n8n 构建的自动化工作流，每天定时从多个 RSS 源抓取 AI 和科技领域的新闻，通过 DeepSeek 大模型筛选出 5 条对普通人生活最有价值的动态，自动推送到飞书群，并同步存档到飞书多维表格。整个过程全自动运行，无需人工干预，帮助个人或团队高效获取行业资讯，节省每日信息筛选时间。

English
This is an automated workflow built with n8n. It periodically fetches AI and tech news from multiple RSS sources, uses the DeepSeek LLM to filter the 5 most valuable updates for daily life, automatically pushes them to a Feishu group chat, and archives them into a Feishu multidimensional table. The entire process runs automatically without human intervention, helping individuals or teams efficiently stay informed and save time on daily information filtering.
使用方法
1️⃣ 导入工作流
打开 n8n → Import from File → 选择 workflow.json

2️⃣ 替换占位符（必需）
占位符	在哪里找
YOUR_APP_ID	飞书开发者后台 → 应用凭证
YOUR_APP_SECRET	飞书开发者后台 → 应用凭证
YOUR_FEISHU_WEBHOOK	飞书群 → 群机器人 → 自定义机器人 → Webhook 地址
YOUR_APP_TOKEN	多维表格链接中 base/ 后面的那串
YOUR_TABLE_ID	多维表格链接中 table= 后面的那串
YOUR_DEEPSEEK_API_KEY	DeepSeek 平台 → API Keys
替换位置：

YOUR_APP_ID / YOUR_APP_SECRET → 在“获取飞书 token”的 HTTP Request 节点的 Body 里

YOUR_FEISHU_WEBHOOK → 在“发送飞书消息”的 HTTP Request 节点的 URL 里

YOUR_APP_TOKEN / YOUR_TABLE_ID → 在“写入多维表格”的 HTTP Request 节点的 URL 里

YOUR_DEEPSEEK_API_KEY → 在“调用 DeepSeek”的 HTTP Request 节点的 Authentication 里

3️⃣ 配置 RSS 源（可选）
在 RSS Read 节点的 URL 里填你要订阅的地址，推荐：

量子位：https://www.qbitai.com/feed

机器之心：https://www.jiqizhixin.com/rss

36氪：https://36kr.com/feed

爱范儿：https://www.ifanr.com/feed

就这么简单，把上面 6 个占位符替换成你自己的值，激活工作流就行。 😊
