# 微信股票分析插件 (XYBotv2) 🤖📈

[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

一个专为 **XYBotv2** 设计的强大微信插件，可以直接在您的聊天界面中实现实时股票数据分析和投资建议。此插件利用 `akshare` 库获取股票数据，并可选择与 Dify AI 服务集成，以进行深入的分析和建议。

## 功能特性 ✨

-   **实时股票分析**：获取A股、港股、美股、ETF和LOF的最新股票数据。
-   **技术指标分析**：计算关键技术指标，如RSI、MACD和移动平均线。
-   **AI驱动的洞察**：（可选）与Dify AI集成，提供全面的股票分析和投资建议。
-   **可定制**：通过 `config.toml` 轻松配置插件，以满足您的特定需求。
-   **定时市场总结**：自动将每日市场总结发送到指定的聊天群组。
-   **易于使用**：只需发送包含股票分析命令和股票代码的文本消息。
-   **专为 XYBotv2 优化**: 无缝集成到 XYBotv2 框架中。

## 依赖项 📦

在使用股票分析插件之前，请确保您已安装以下依赖项：

-   `akshare`：用于检索股票数据。
    ```bash
    pip install akshare
    ```
-   `loguru`：用于增强的日志记录。
    ```bash
    pip install loguru
    ```
-   `aiohttp`：用于异步HTTP请求。
    ```bash
    pip install aiohttp
    ```
-   `numpy`：用于数值计算。
    ```bash
    pip install numpy
    ```
-   `toml`：用于解析toml文件。
    ```bash
    pip install toml
    ```

**重要提示**: 确保这些依赖已安装在 XYBotv2 的 Python 环境中。

## 安装 ⚙️

1.  将插件文件（例如 `StockAnalysis.py` 和 `config.toml`）放置在 XYBotv2 的插件目录中。
2.  使用 `pip install -r requirements.txt` 安装所需的依赖项（如果创建了 `requirements.txt`）。或者逐个安装上面列出的依赖项。 确保在 **XYBotv2 的 Python 环境**中执行此操作。
3.  在 `config.toml` 中配置插件设置。
4.  重启 XYBotv2 以加载插件。

## 配置 📝

该插件通过 `config.toml` 文件进行配置。以下是可用设置的细分：

```toml
[StockAnalysis]
enable = true  # 启用或禁用插件
commands = ["分析股票", "股票分析", "analyze"]  # 触发股票分析的命令

[StockAnalysis.Settings]
default_market = ""  # 默认市场类型（A、HK、US、ETF、LOF）。留空以自动检测。
data_cache_days = 30  # 缓存股票数据的天数

[StockAnalysis.Dify]
enable = true  # 启用或禁用 Dify AI 集成
api-key = "您的_DIFY_API_密钥"  # 您的 Dify API 密钥
base-url = "您的_DIFY_基本_URL"  # 您的 Dify 基本 URL
http-proxy = ""  # HTTP 代理（如果需要）
