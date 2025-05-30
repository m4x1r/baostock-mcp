# A 股数据 MCP SSE 服务器

本项目提供中国 A 股市场数据分析工具，使用 MCP (Message Channel Pattern) 框架，通过 SSE (Server-Sent Events) 技术提供实时数据流服务。

## 功能特点

- 基于 FastMCP 框架构建
- 使用 SSE 技术实现服务器向客户端的实时推送
- 支持跨域请求 (CORS)
- 提供丰富的 A 股市场数据分析工具
- 包含简单的 Web 客户端用于测试和演示

## 环境要求

- Python 3.11 或更高版本
- 依赖包见 `pyproject.toml`

## 安装

1. 克隆仓库：

```bash
git clone https://github.com/your-username/baostock-mcp.git
cd baostock-mcp
```

2. 安装依赖：

```bash
uv sync
```

## 启动服务器

可以通过环境变量配置服务器：

```bash
# 默认配置：监听所有网卡，端口 8000
uv run mcp_server.py

# 自定义配置
MCP_HOST=127.0.0.1 MCP_PORT=8080 uv run mcp_server.py
```

## 使用 Web 客户端

1. 启动服务器后,运行一下命令启动客户端测试工具

```bash
npx @modelcontextprotocol/inspector node build/index.js
```

2. `Transport Type`选择`SSE`
3. 在 `URL` 地址框中输入服务器地址 `http://localhost:8080/sse`
4. 点击"Connect"按钮
5. 连接成功后，选择 Tool->List Tool，在列表中选择借口进行测试。

## 数据工具

系统提供以下主要工具类别：

1. 股票市场工具 - 查询个股信息、价格数据等
2. 财务报表工具 - 查询公司财务指标和报表数据
3. 指数工具 - 查询各类指数数据和成分股
4. 市场概览工具 - 获取市场整体情况和行业数据
5. 宏观经济工具 - 查询宏观经济指标
6. 日期工具 - 处理交易日期和时间范围
7. 分析工具 - 执行各种技术和基本面分析

## 注意事项

- 服务提供的数据分析基于公开市场信息，不构成投资建议，仅供参考
- 使用日期相关功能时，请始终使用系统提供的工具获取正确的交易日期
- 默认配置下，服务器绑定到所有网卡 (0.0.0.0)，在生产环境中应考虑安全限制
