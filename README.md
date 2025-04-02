# MCP-Client-For-Weather-Example

MCP-Client-For-Weather-Example 是一个基于 MCP（Modular Communication Protocol）的客户端和服务器项目，支持通过 LLM 的大语言模型与工具交互，并提供天气查询功能。

## 功能特性

- **MCP 客户端**：支持与 MCP 服务器通信，调用工具并处理查询。
- **天气查询服务**：通过 OpenWeather API 查询指定城市的天气信息。
- **环境变量支持**：通过 `.env` 文件配置 API 密钥和其他参数。
- **异步支持**：使用 `asyncio` 和 `httpx` 实现高效的异步通信。

## 文件结构

```bash
├── .env # 环境变量配置文件
├── .gitignore # Git 忽略文件
├── client.py # MCP 客户端实现
├── mcp_weather_server.py # 天气查询服务实现
├── pyproject.toml # 项目依赖配置文件
└── README.md # 项目说明文件
```

## 环境配置

### 1. 安装依赖

确保已安装 Python 3 或更高版本。然后运行以下命令安装依赖：

```bash
# 使用 uv
pip install uv
uv add mcp httpx openai
# 创建虚拟环境
uv venv
# 激活虚拟环境
source .venv/bin/activate
```

### 2. 配置环境变量

在项目根目录下创建 .env 文件，并添加以下内容：

> 这里使用的[硅基智能的 API](https://cloud.siliconflow.cn/models),天气API去 https://openweathermap.org 注册

```env
OPENAI_API_KEY=你的OpenAI API密钥
BASE_URL=https://api.siliconflow.cn/v1 # <你的OpenAI API基础URL>
MODEL=使用的模型名称
WEATHER_API_KEY=你的OpenWeather API密钥
```
## 使用方法

1. 运行以下命令启动 MCP 客户端并连接到服务器：

```bash
python client.py mcp_weather_server.py
```

2. 启动后，输入城市名称（英文）即可查询天气信息。例如：
> 回答效果取决于模型本身，你的输出可能有些出入。

```bash
你: 今天北京天气怎样？
🤖 LLM: 北京的天气情况如下：
- 温度：10.94°C
- 湿度：15%
- 风速：4 m/s
- 天气：晴，少云
今天的北京天气晴朗，温度适宜，适合外出活动。请注意保暖，因为早晨和晚上的气温可能会有所下降
```

3. 退出客户端
   输入 quit 退出 MCP 客户端。

## 项目依赖

```bash
Python 3+
httpx - 异步 HTTP 客户端
mcp - Modular Communication Protocol
openai - OpenAI API 客户端
python-dotenv - 环境变量加载工具
```

## 开发指南

### 代码格式化

使用 pycharm 快捷键，进行格式化

### 单元测试

目前项目未包含单元测试模块，建议后续添加测试以提高代码质量。

### 许可证

本项目未指定许可证，默认保留所有权利。如需使用，请联系项目作者。

### 贡献

欢迎提交 Issue 和 Pull Request 来改进本项目。

### 联系方式

如有问题，请通过 GitHub Issue 提交反馈。


## 感谢
- 【[MCP 实战：调用DeepSeek实现MCP客户端和服务端快速搭建](https://deepseek.csdn.net/67e383ff45a25f3de59f7bb0.html)】
