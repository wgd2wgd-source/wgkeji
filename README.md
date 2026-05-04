# 每日AI科技新闻日报系统
# Daily AI Tech News Report System

[English Version Below](#english)

## 功能介绍 Features

这是一个自动化的每日AI科技新闻收集系统，具有以下功能：

✅ **自动收集新闻** - 从多个来源（ArXiv、Hacker News、Google News等）自动收集最新科技新闻  
✅ **智能分类** - 自动将新闻分为11个科技类别  
✅ **重要程度排序** - 按照重要程度对新闻进行排序  
✅ **邮件推送** - 每日自动发送邮件通知到 wgd8wgd@gmail.com  
✅ **GitHub集成** - 自动创建GitHub Issues保存每日报告  
✅ **定时运行** - 使用GitHub Actions每天自动执行  

## 科技类别 Categories

- 🤖 AI（人工智能）
- 🦾 机器人（Robotics）
- 🔬 基础科学（Fundamental Science）
- ⚛️ 物理（Physics）
- 🧬 生物（Biology）
- 🧪 化学（Chemistry）
- 🏥 医疗（Medical）
- 🚀 航空航天（Aerospace）
- 🧠 心理学（Psychology）
- 👥 社会学（Sociology）
- 💻 信息工程（Information Engineering）

## 快速开始 Quick Start

### 1. 配置邮件服务
在仓库设置中添加以下Secrets：

| Secret 名称 | 说明 |
|---|---|
| `SMTP_SERVER` | SMTP服务器（如：smtp.gmail.com） |
| `SMTP_PORT` | SMTP端口（通常为587） |
| `SENDER_EMAIL` | 发送邮箱地址 |
| `SENDER_PASSWORD` | 邮箱密码或应用密码 |

**设置步骤：**
1. 访问 https://github.com/wgd2wgd-source/wgkeji/settings/secrets/actions
2. 点击 "New repository secret"
3. 添加上述4个Secret

**Gmail 用户提示：**
- 使用[应用密码](https://myaccount.google.com/apppasswords)而不是账户密码
- 确保2步验证已启用

### 2. 本地运行

```bash
# 安装依赖
pip install -r requirements.txt

# 收集新闻
python scripts/news_collector.py

# 发送邮件（需要配置环境变量）
export SMTP_SERVER=smtp.gmail.com
export SMTP_PORT=587
export SENDER_EMAIL=your-email@gmail.com
export SENDER_PASSWORD=your-app-password

python scripts/send_email.py
```

### 3. 自动运行

系统已配置自动运行：
- ⏰ **执行时间**：每天 UTC 08:00（北京时间 16:00）
- 🚀 **手动触发**：在Actions标签页手动运行工作流

## 新闻来源 News Sources

| 来源 | 类型 | 说明 |
|---|---|---|
| ArXiv | 学术论文 | 最新学术论文和研究 |
| Hacker News | 技术新闻 | 科技社区热点新闻 |
| Google News | 综合新闻 | 全球科技新闻聚合 |
| Nature | 学术期刊 | 自然科学期刊 |
| MIT Technology Review | 科技评论 | 前沿技术分析 |

## 报告格式 Report Format

每份日报包含以下信息：

```
## 类目 Category
### 1. 标题 Title
**Source:** 信息源
**Summary:** 内容提要
**Link:** [原文链接](url)
```

## 项目结构 Project Structure

```
wgkeji/
├── config/
│   └── daily_news_config.json      # 配置文件
├── scripts/
│   ├── news_collector.py           # 新闻收集脚本
│   └── send_email.py               # 邮件发送脚本
├── reports/
│   └── daily_news_YYYYMMDD.md      # 每日报告
├── .github/
│   └── workflows/
│       └── daily_news_report.yml   # GitHub Actions工作流
├── requirements.txt                # Python依赖
└── README.md                       # 本文件
```

## 配置选项 Configuration

编辑 `config/daily_news_config.json` 来自定义设置：

```json
{
  "email": "wgd8wgd@gmail.com",
  "categories": [
    "AI", "机器人", "基础科学", ...
  ],
  "news_sources": [...]
}
```

## 故障排除 Troubleshooting

### 邮件未发送
- ✅ 检查GitHub Secrets是否正确配置
- ✅ 检查邮箱是否支持第三方应用（Gmail需使用应用密码）
- ✅ 查看Actions日志获取错误信息

### 没有收集到新闻
- ✅ 检查网络连接
- ✅ 验证新闻源是否可访问
- ✅ 查看news_collector.py日志

### 报告没有保存
- ✅ 检查`reports/`目录权限
- ✅ 确保Git配置正确

## 许可证 License

MIT License

---

## English

# Daily AI Tech News Report System

An automated system that collects AI and tech news daily from multiple sources, categorizes them, ranks by importance, and sends email notifications.

### Features

✅ **Auto News Collection** - Collects from ArXiv, Hacker News, Google News  
✅ **Smart Categorization** - 11 tech categories  
✅ **Importance Ranking** - Sorted by relevance  
✅ **Email Notifications** - Daily automated emails  
✅ **GitHub Integration** - Saves reports as GitHub Issues  
✅ **Scheduled Execution** - Runs daily via GitHub Actions  

### Configuration

Add these secrets to your GitHub repository settings:
- `SMTP_SERVER`
- `SMTP_PORT`
- `SENDER_EMAIL`
- `SENDER_PASSWORD`

### Usage

```bash
pip install -r requirements.txt
python scripts/news_collector.py
python scripts/send_email.py
```

### Scheduled Execution

Runs automatically every day at 08:00 UTC via GitHub Actions workflow.

See the Chinese section above for detailed configuration instructions.
