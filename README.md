# 货币与石油价格服务器 Currency And Oil

Zenrus MCP Server 是一个提供实时货币汇率和石油价格的服务器，支持多种计算功能，适用于金融分析和自动化工具集成。
Zenrus MCP Server is a server that provides real-time currency exchange rates and oil prices, supports multiple computing functions, and is suitable for financial analysis and automation tool integration.## 工具列表 Tool List

本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。 本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。

| 工具 Tool   | 描述 Description         |
|-------|--------------------|
| get_usd_rate | Get current USD/RUB exchange rate from zenrus.ru |
| get_eur_rate | Get current EUR/RUB exchange rate from zenrus.ru |
| get_brent_usd_rate | Get current Brent crude oil price in USD per barrel from zenrus.ru |
| get_brent_rub_rate | Get current Brent crude oil price in RUB per barrel from zenrus.ru |
| calculate_barrels_for_rub | Calculate how many barrels of Brent crude oil can be purchased for a given amount in Russian Rubles |
| calculate_barrels_for_usd | Calculate how many barrels of Brent crude oil can be purchased for a given amount in US Dollars |
| calculate_barrels_for_eur | Calculate how many barrels of Brent crude oil can be purchased for a given amount in Euros |


## 检查服务 ## Inspector

工具在线测试： [https://mcp.xiaobenyang.com/inspector/1777316659852291](https://mcp.xiaobenyang.com/inspector/1777316659852291)

Online Tool test [https://mcp.xiaobenyang.com/inspector/1777316659852291](https://mcp.xiaobenyang.com/inspector/1777316659852291)

## 服务配置 MCP Server Config


> #### 如何获取 XBY-APIKEY ？ How to get XBY-APIKEY ?
> 访问小笨羊科技网站 [https://xiaobenyang.com](https://xiaobenyang.com)，注册用户即可获得APIKEY
> Visit XiaoBenYang website [https://xiaobenyang.com](https://xiaobenyang.com), register and get the APIKEY.

### SSE
```json
{
  "mcpServers": {
    "货币与石油价格服务器": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "sse",
      "url": "https://mcp.xiaobenyang.com/1777316659852291/sse"
    }
  }
}
```
### STREAMABLE HTTP
```json
{
  "mcpServers": {
    "货币与石油价格服务器": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "streamable_http",
      "url": "https://mcp.xiaobenyang.com/1777316659852291/mcp"
    }
  }
}
```
### STDIO
```json
{
    "mcpServers": {
        "货币与石油价格服务器": {
          "command": "npx",
          "args": [
            "-y",
            "xiaobenyang-mcp"
          ],
          "env": {
            "XBY_APIKEY": "<YOUR_XBY_APIKEY>",
            "mcpId": "1777316659852291",
          },
          "transport": "stdio"
        }
      }
}

```
