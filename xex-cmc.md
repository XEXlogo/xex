# OpenAPI definition


**Description**:OpenAPI definition


**Contacts**:


**Version**:v0


[TOC]



# CMC Market


## /cmc/trades/market_pair


**url**:`/cmc/trades/market_pair`


**method**:`GET`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`application/json`


**Note**:<p>查询交易对最近成交记录，CMC使用</p>



**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|market_pair||query|true|string||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200|OK|GenericResultListTradeHistoryCmcResponse|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|code|业务状态码|string||
|data|业务数据|array|TradeHistoryCmcResponse|
|&emsp;&emsp;price|成交价格|number||
|&emsp;&emsp;type|成交方向|string||
|&emsp;&emsp;timestamp|时间戳，毫秒|integer(int64)||
|&emsp;&emsp;trade_id|成交id|integer(int64)||
|&emsp;&emsp;quote_volume|quote交易量|number||
|&emsp;&emsp;base_volume|base交易量|number||
|succ||boolean||
|msg|提示消息|string||


**Response Example**:
```javascript
{
	"code": "",
	"data": [
		{
			"price": 0,
			"type": "",
			"timestamp": 0,
			"trade_id": 0,
			"quote_volume": 0,
			"base_volume": 0
		}
	],
	"succ": true,
	"msg": ""
}
```


## /cmc/ticker


**url**:`/cmc/ticker`


**method**:`GET`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`application/json`


**Note**:<p>批量查询查询交易对交易量和最新价，CMC使用</p>



**Params**:


暂无


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200|OK|GenericResultMapStringTickerCmcResponse|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|code|业务状态码|string||
|data|业务数据|TickerCmcResponse|TickerCmcResponse|
|&emsp;&emsp;base_id|base币种id|integer(int32)||
|&emsp;&emsp;quote_volume|quote币种成交量|number||
|&emsp;&emsp;quote_id|quote币种id|integer(int32)||
|&emsp;&emsp;base_volume|base币种成交量|number||
|&emsp;&emsp;last_price|最新价|number||
|&emsp;&emsp;isFrozen|是否冻结|integer(int32)||
|succ||boolean||
|msg|提示消息|string||


**Response Example**:
```javascript
{
	"code": "",
	"data": {
		"additionalProperties1": {
			"base_id": 0,
			"quote_volume": 0,
			"quote_id": 0,
			"base_volume": 0,
			"last_price": 0,
			"isFrozen": 0
		}
	},
	"succ": true,
	"msg": ""
}
```


## /cmc/spot/market


**url**:`/cmc/spot/market`


**method**:`GET`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`application/json`


**Note**:<p>查询交易对行情信息，CMC使用</p>



**Params**:


暂无


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200|OK|GenericResultListMarketCmcResponse|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|code|业务状态码|string||
|data|业务数据|array|MarketCmcResponse|
|&emsp;&emsp;time|时间戳，毫秒|integer(int64)||
|&emsp;&emsp;trading_pair|交易对|string||
|&emsp;&emsp;quote_volume|quote成交量|number||
|&emsp;&emsp;base_volume|base成交量|number||
|&emsp;&emsp;last_price|最新价格|number||
|&emsp;&emsp;lowest_ask|最低卖价|number||
|&emsp;&emsp;highest_bid|最高买价格|number||
|&emsp;&emsp;highest_price_24h|cmc行情|number||
|&emsp;&emsp;lowest_price_24h|24小时最低价|number||
|&emsp;&emsp;price_change_percent_24h|24小时涨跌幅|number||
|succ||boolean||
|msg|提示消息|string||


**Response Example**:
```javascript
{
	"code": "",
	"data": [
		{
			"time": 0,
			"trading_pair": "",
			"quote_volume": 0,
			"base_volume": 0,
			"last_price": 0,
			"lowest_ask": 0,
			"highest_bid": 0,
			"highest_price_24h": 0,
			"lowest_price_24h": 0,
			"price_change_percent_24h": 0
		}
	],
	"succ": true,
	"msg": ""
}
```


## /cmc/spec


**url**:`/cmc/spec`


**method**:`GET`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`application/json`


**Note**:<p>查询合约类型，CMC使用</p>



**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|contractName||query|true|string||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200|OK|GenericResultContractSpecificationsResponse|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|code|业务状态码|string||
|data||ContractSpecificationsResponse|ContractSpecificationsResponse|
|&emsp;&emsp;contract_type|交易对|string||
|&emsp;&emsp;contract_price_currency|quote成交量|number||
|&emsp;&emsp;contract_price|价格|number||
|succ||boolean||
|msg|提示消息|string||


**Response Example**:
```javascript
{
	"code": "",
	"data": {
		"contract_type": "",
		"contract_price_currency": 0,
		"contract_price": 0
	},
	"succ": true,
	"msg": ""
}
```


## /cmc/orderbook


**url**:`/cmc/orderbook`


**method**:`GET`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`application/json`


**Note**:<p>查询合约交易对买卖盘，CMC使用</p>



**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|contractName||query|true|string||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200|OK|GenericResultOrderBookCmcResponse|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|code|业务状态码|string||
|data||OrderBookCmcResponse|OrderBookCmcResponse|
|&emsp;&emsp;asks|卖盘|array|array|
|&emsp;&emsp;bids|买盘|array|array|
|&emsp;&emsp;timestamp|时间戳，单位毫秒|integer(int64)||
|&emsp;&emsp;ticker_id|交易对|string||
|succ||boolean||
|msg|提示消息|string||


**Response Example**:
```javascript
{
	"code": "",
	"data": {
		"asks": [],
		"bids": [],
		"timestamp": 0,
		"ticker_id": ""
	},
	"succ": true,
	"msg": ""
}
```


## /cmc/orderbook/market_pair


**url**:`/cmc/orderbook/market_pair`


**method**:`GET`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`application/json`


**Note**:<p>查询交易对买卖盘，CMC使用</p>



**Params**:


| name | description | in    | require | type | schema |
| -------- | -------- | ----- | -------- | -------- | ------ |
|market_pair||query|true|string||


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200|OK|GenericResultOrderBookCmcResponse|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|code|业务状态码|string||
|data||OrderBookCmcResponse|OrderBookCmcResponse|
|&emsp;&emsp;asks|卖盘|array|array|
|&emsp;&emsp;bids|买盘|array|array|
|&emsp;&emsp;timestamp|时间戳，单位毫秒|integer(int64)||
|&emsp;&emsp;ticker_id|交易对|string||
|succ||boolean||
|msg|提示消息|string||


**Response Example**:
```javascript
{
	"code": "",
	"data": {
		"asks": [],
		"bids": [],
		"timestamp": 0,
		"ticker_id": ""
	},
	"succ": true,
	"msg": ""
}
```


## /cmc/futures/market


**url**:`/cmc/futures/market`


**method**:`GET`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`application/json`


**Note**:<p>查询交易对行情信息，CMC使用合约</p>



**Params**:


暂无


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200|OK|GenericResultListContractMarketCmcResponse|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|code|业务状态码|string||
|data|业务数据|array|ContractMarketCmcResponse|
|&emsp;&emsp;ticker_id|交易对|string||
|&emsp;&emsp;base_currency|base币种|string||
|&emsp;&emsp;quote_currency|quote币种|string||
|&emsp;&emsp;quote_volume|quote币种交易量|number||
|&emsp;&emsp;base_volume|base币种交易量|number||
|&emsp;&emsp;high|24小时最高价|number||
|&emsp;&emsp;low|24小时最低价|number||
|&emsp;&emsp;ask|卖一价格|number||
|&emsp;&emsp;bid|买一价格|number||
|&emsp;&emsp;last_price|最新价格|number||
|&emsp;&emsp;index_price|标记价格|number||
|&emsp;&emsp;open_interest_usd|未平仓数量对应价值（多+空）|number||
|&emsp;&emsp;open_interest|未平仓数量（多+空）|number||
|&emsp;&emsp;funding_rate|资金费率|number||
|&emsp;&emsp;next_funding_rate_timestamp|下次计算资金费率时间|integer(int64)||
|&emsp;&emsp;product_type|合约类型|string||
|succ||boolean||
|msg|提示消息|string||


**Response Example**:
```javascript
{
	"code": "",
	"data": [
		{
			"ticker_id": "",
			"base_currency": "",
			"quote_currency": "",
			"quote_volume": 0,
			"base_volume": 0,
			"high": 0,
			"low": 0,
			"ask": 0,
			"bid": 0,
			"last_price": 0,
			"index_price": 0,
			"open_interest_usd": 0,
			"open_interest": 0,
			"funding_rate": 0,
			"next_funding_rate_timestamp": 0,
			"product_type": ""
		}
	],
	"succ": true,
	"msg": ""
}
```


## /cmc/assets


**url**:`/cmc/assets`


**method**:`GET`


**produces**:`application/x-www-form-urlencoded`


**consumes**:`application/json`


**Note**:<p>查询所有币种资产，CMC使用</p>



**Params**:


暂无


**Status**:


| code | description | schema |
| -------- | -------- | ----- | 
|200|OK|GenericResultMapStringAssetsCmcResponse|


**Response Params**:


| name | description | type | schema |
| -------- | -------- | ----- |----- | 
|code|业务状态码|string||
|data|业务数据|AssetsCmcResponse|AssetsCmcResponse|
|&emsp;&emsp;unified_cryptoasset_id|资产id|integer(int64)||
|&emsp;&emsp;name|币种名称|string||
|&emsp;&emsp;can_withdraw|是否可提现|integer(int32)||
|&emsp;&emsp;can_deposit|cmc行情|integer(int32)||
|&emsp;&emsp;min_withdraw|最小提现|number||
|&emsp;&emsp;max_withdraw|最大提现|number||
|succ||boolean||
|msg|提示消息|string||


**Response Example**:
```javascript
{
	"code": "",
	"data": {
		"additionalProperties1": {
			"unified_cryptoasset_id": 0,
			"name": "",
			"can_withdraw": 0,
			"can_deposit": 0,
			"min_withdraw": 0,
			"max_withdraw": 0
		}
	},
	"succ": true,
	"msg": ""
}
```