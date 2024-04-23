# ICDex Data API

## Instructions:

- Data update interval: 1 minutes
- Timestamps are expressed in milliseconds
- Values in Json are all in double quotes
- All amounts and prices have been converted to a human readable format

## /v1/pairs

Returns information about all pairs.

**Endpoint：** https://gwhbq-7aaaa-aaaar-qabya-cai.raw.icp0.io/v1/pairs

**Response Example**

````json
{
    "provider":"ICDex",
    "provider_logo":"https://iclight.io/static/img/icdex-1.c1efde9e.png",
    "provider_URL":"https://iclight.io/ICDex/",
    "matching_mode":"Orderbook",
    "links":[
        {
            "title":"Twitter",
            "link":"https://twitter.com/ICLighthouse"
        },
        {
            "title":"Discord",
            "link":"https://discord.gg/FQZFGGq7zv"
        }
    ],
    "pairs":{
        "xsi2v-cyaaa-aaaaq-aabfq-cai_ryjl3-tyaaa-aaaaa-aaaba-cai":{
            "name":"icdex:MOD_ICP",
            "url":"https://iclight.io/ICDex/MOD/ICP",
            "base_id":"xsi2v-cyaaa-aaaaq-aabfq-cai",
            "base_name":"MOD",
            "base_symbol":"MOD",
            "quote_id":"ryjl3-tyaaa-aaaaa-aaaba-cai",
            "quote_name":"ICP",
            "quote_symbol":"ICP"
        },
        "6rdgd-kyaaa-aaaaq-aaavq-cai_ryjl3-tyaaa-aaaaa-aaaba-cai":{
            "name":"icdex:HOT_ICP",
            "url":"https://iclight.io/ICDex/HOT/ICP",
            "base_id":"6rdgd-kyaaa-aaaaq-aaavq-cai",
            "base_name":"HOT",
            "base_symbol":"HOT",
            "quote_id":"ryjl3-tyaaa-aaaaa-aaaba-cai",
            "quote_name":"ICP",
            "quote_symbol":"ICP"
        },
        "2ouva-viaaa-aaaaq-aaamq-cai_ryjl3-tyaaa-aaaaa-aaaba-cai":{
            "name":"icdex:CHAT_ICP",
            "url":"https://iclight.io/ICDex/CHAT/ICP",
            "base_id":"2ouva-viaaa-aaaaq-aaamq-cai",
            "base_name":"CHAT",
            "base_symbol":"CHAT",
            "quote_id":"ryjl3-tyaaa-aaaaa-aaaba-cai",
            "quote_name":"ICP",
            "quote_symbol":"ICP"
        }
    }
}
````

## /v1/latest

Returns the latest data for all pairs.

**Endpoint：** https://gwhbq-7aaaa-aaaar-qabya-cai.raw.icp0.io/v1/latest

**Response Example**

````json
{
    "imeri-bqaaa-aaaai-qnpla-cai_ryjl3-tyaaa-aaaaa-aaaba-cai":{
        "base_id":"imeri-bqaaa-aaaai-qnpla-cai",
        "base_name":"OT",
        "base_symbol":"OT",
        "quote_id":"ryjl3-tyaaa-aaaaa-aaaba-cai",
        "quote_name":"ICP",
        "quote_symbol":"ICP",
        "last_price":"0.000244",
        "base_volume":"111287007.000000",
        "quote_volume":"127721.609712",
        "base_24h_volume":"111287007.000000",
        "quote_24h_volume":"127721.609712",
        "usd_volume": "57654.389786", 
        "usd_24h_volume": "10.000000", 
        "change_24h": "0.010000"
    },
    "zfcdd-tqaaa-aaaaq-aaaga-cai_ryjl3-tyaaa-aaaaa-aaaba-cai":{
        "base_id":"zfcdd-tqaaa-aaaaq-aaaga-cai",
        "base_name":"SNS1",
        "base_symbol":"SNS1",
        "quote_id":"ryjl3-tyaaa-aaaaa-aaaba-cai",
        "quote_name":"ICP",
        "quote_symbol":"ICP",
        "last_price":"219.350100",
        "base_volume":"162852.588000",
        "quote_volume":"1628044.966935",
        "base_24h_volume":"111287007.000000",
        "quote_24h_volume":"127721.609712",
        "usd_volume": "57654.389786", 
        "usd_24h_volume": "10.000000", 
        "change_24h": "0.010000"
    }
}
````

## /v1/subgraph/

Returns the history of trades for all pairs.

**Endpoint:** https://gwhbq-7aaaa-aaaar-qabya-cai.raw.icp0.io/v1/subgraph/

https://gwhbq-7aaaa-aaaar-qabya-cai.raw.icp0.io/v1/subgraph/[start_ts]/[length]/[pair_id]/

**Parameters:**

- start_ts: Time filter `start_ts` is a timestamp expressed in milliseconds. Not specifying this value means that the most recent data is returned.
- length: Specify the size of the returned dataset, The default value of `length` is 500 and the maximum value is 1000.
- pair_id: Specify a trading pair, default value of `pair_id` is "all". e.g. `zfcdd-tqaaa-aaaaq-aaaga-cai_ryjl3-tyaaa-aaaaa-aaaba-cai`.

**Notes:**

- The above parameters are optional and are entered in the order `/start_ts/length/pair_id/`.
- E.g.   
  https://gwhbq-7aaaa-aaaar-qabya-cai.raw.icp0.io/v1/subgraph/1695378900000/100/  
  https://gwhbq-7aaaa-aaaar-qabya-cai.raw.icp0.io/v1/subgraph//100/zfcdd-tqaaa-aaaaq-aaaga-cai_ryjl3-tyaaa-aaaaa-aaaba-cai  
  https://gwhbq-7aaaa-aaaar-qabya-cai.raw.icp0.io/v1/subgraph///zfcdd-tqaaa-aaaaq-aaaga-cai_ryjl3-tyaaa-aaaaa-aaaba-cai

**Response Example** 

````json
{
    "trades":[
        {
            "fromAmount":"1.120000",
            "toAmount":"400.000000",
            "id":"0000000189ca1e33b386c2a9cfa7746fccec6456129df1dd846ad2f3eaff6ad7_0",
            "timestamp":"1695543479434",
            "pair":{
                "pairId":"vtrom-gqaaa-aaaaq-aabia-cai_ryjl3-tyaaa-aaaaa-aaaba-cai",
                "fromToken":{
                    "tokenId":"ryjl3-tyaaa-aaaaa-aaaba-cai",
                    "symbol":"ICP"
                },
                "toToken":{
                    "tokenId":"vtrom-gqaaa-aaaaq-aabia-cai",
                    "symbol":"BOOM"
                }
            }
        },
        {
            "fromAmount":"400.000000",
            "toAmount":"1.120000",
            "id":"0000001922b900a3578c710a6585092c50ffa3bae89d26e77e633f7978343b3c_2",
            "timestamp":"1695543479434",
            "pair":{
                "pairId":"vtrom-gqaaa-aaaaq-aabia-cai_ryjl3-tyaaa-aaaaa-aaaba-cai",
                "fromToken":{
                    "tokenId":"vtrom-gqaaa-aaaaq-aabia-cai",
                    "symbol":"BOOM"
                },
                "toToken":{
                    "tokenId":"ryjl3-tyaaa-aaaaa-aaaba-cai",
                    "symbol":"ICP"
                }
            }
        }
    ]
}
````



## /v1/pools

Returns all MM pools for the pairs.

**Endpoint** https://gwhbq-7aaaa-aaaar-qabya-cai.raw.icp0.io/v1/pools

**Response Example** 

````json
{
    "pools":[
        {
            "poolId":"qhssc-vaaaa-aaaak-adh2a-cai",
            "name":"OT/ICP - Orderbook",
            "pair":"OT_ICP (qhssc-vaaaa-aaaak-adh2a-cai)",
            "pairId": "f54if-eqaaa-aaaaq-aacea-cai_ryjl3-tyaaa-aaaaa-aaaba-cai", 
            "pairLink":"https://iclight.io/ICDex/OT/ICP",
            "logo":"",
            "poolRewards":[
                "ICL"
            ],
            "apr":"0",
            "totalStaked":"0.000000"
        },
        {
            "poolId":"32fn4-qqaaa-aaaak-ad65a-cai",
            "name":"SNS1/ICP - Orderbook",
            "pair":"SNS1_ICP (32fn4-qqaaa-aaaak-ad65a-cai)",
            "pairId": "zfcdd-tqaaa-aaaaq-aaaga-cai_ryjl3-tyaaa-aaaaa-aaaba-cai", 
            "pairLink":"https://iclight.io/ICDex/SNS1/ICP",
            "logo":"",
            "poolRewards":[
                "ICL"
            ],
            "apr":"0",
            "totalStaked":"0.000000"
        }
    ],
    "pairs": [
        {
            "pair": "NTN_ICP", 
            "pairId": "f54if-eqaaa-aaaaq-aacea-cai_ryjl3-tyaaa-aaaaa-aaaba-cai", 
            "tvl": "6340.462622"
        }, 
        {
            "pair": "MOD_ICP", 
            "pairId": "xsi2v-cyaaa-aaaaq-aabfq-cai_ryjl3-tyaaa-aaaaa-aaaba-cai", 
            "tvl": "1649.350668"
        }
    ]
}
````

## /v1/pools/tvls

Returns the TVL of the pairs.

**Endpoint** https://gwhbq-7aaaa-aaaar-qabya-cai.raw.icp0.io/v1/pools/tvls

**Response Example** 

````json
{
    "pairs": [
        {
            "pair": "NTN_ICP", 
            "pairId": "f54if-eqaaa-aaaaq-aacea-cai_ryjl3-tyaaa-aaaaa-aaaba-cai", 
            "tvl": "6340.462622"
        }, 
        {
            "pair": "MOD_ICP", 
            "pairId": "xsi2v-cyaaa-aaaaq-aabfq-cai_ryjl3-tyaaa-aaaaa-aaaba-cai", 
            "tvl": "1649.350668"
        }
    ]
}
````

## /v1/stats

Returns ICDex volume and total TVL statistics.

**Endpoint** https://gwhbq-7aaaa-aaaar-qabya-cai.raw.icp0.io/v1/stats

**Response Example** 

````json
{
    "result": [
        {"time": "1712707200000", "usd_total_vol": "1249637338.525661", "usd_24h_vol": "177388.379215", "usd_total_tvl": "5118904.907997"}, 
        {"time": "1712620800000", "usd_total_vol": "1249481442.492603", "usd_24h_vol": "186421.669629", "usd_total_tvl": "5082314.304459"}, 
        {"time": "1712534400000", "usd_total_vol": "1249153025.173038", "usd_24h_vol": "108145.434066", "usd_total_tvl": "5411470.847902"}, 
        {"time": "1712448000000", "usd_total_vol": "1248937390.631374", "usd_24h_vol": "218177.202422", "usd_total_tvl": "5170211.072995"}
    ]
}
````

## /v1/tickers

Returns the latest data for the pairs.

**Endpoint** https://gwhbq-7aaaa-aaaar-qabya-cai.raw.icp0.io/v1/tickers

```json
[
  {
    "ticker_id": "ss2fx-dyaaa-aaaar-qacoq-cai_ryjl3-tyaaa-aaaaa-aaaba-cai",
    "base_currency": "ckETH.ss2fx-dyaaa-aaaar-qacoq-cai",
    "target_currency": "ICP.ryjl3-tyaaa-aaaaa-aaaba-cai",
    "pool_id": "4zugq-fqaaa-aaaar-qadpa-cai",
    "last_price": "239.415000",
    "base_volume": "31.439000", // 24h vol
    "target_volume": "7114.843289", // 24h vol
    "liquidity_in_usd": "31328.649064",
    "bid": "229.219000",
    "ask": "239.415000",
    "high": "239.415000",
    "low": "229.220000"
  },
  {
    "ticker_id": "2ouva-viaaa-aaaaq-aaamq-cai_ryjl3-tyaaa-aaaaa-aaaba-cai",
    "base_currency": "CHAT.2ouva-viaaa-aaaaq-aaamq-cai",
    "target_currency": "ICP.ryjl3-tyaaa-aaaaa-aaaba-cai",
    "pool_id": "52ypw-riaaa-aaaar-qadjq-cai",
    "last_price": "0.038500",
    "base_volume": "11719904.400000",
    "target_volume": "800934.895193",
    "liquidity_in_usd": "349620.577476",
    "bid": "0.037500",
    "ask": "0.038500",
    "high": "0.040500",
    "low": "0.036250"
  }
]
```

## /v1/orderbook

Returns order book data for the specified pair.

**Endpoint** `https://gwhbq-7aaaa-aaaar-qabya-cai.raw.icp0.io/v1/orderbook?ticker_id=<pair_id>[&depth=<depth>]`

E.g. https://gwhbq-7aaaa-aaaar-qabya-cai.raw.icp0.io/v1/orderbook?ticker_id=ss2fx-dyaaa-aaaar-qacoq-cai_ryjl3-tyaaa-aaaaa-aaaba-cai&depth=5

**Parameters:**

- ticker_id: ticker_id or pair_id.
- depth (optional): Orders depth quantity, 0 returns full depth.

```json
{
    "ticker_id": "ss2fx-dyaaa-aaaar-qacoq-cai_ryjl3-tyaaa-aaaaa-aaaba-cai",
    "timestamp": "1712978250696",
    "bids": [
        [
            "229.219000",
            "0.070000"
        ],
        [
            "224.285000",
            "0.071000"
        ],
        [
            "219.457000",
            "0.072000"
        ],
        [
            "214.733000",
            "0.072000"
        ],
        [
            "210.111010",
            "0.237000"
        ]
    ],
    "asks": [
        [
            "239.415000",
            "0.069000"
        ],
        [
            "239.496000",
            "0.077000"
        ],
        [
            "244.682000",
            "0.068000"
        ],
        [
            "250.065000",
            "0.068000"
        ],
        [
            "255.566000",
            "0.067000"
        ]
    ]
}
```

## /v1/historical_trades

Returns the history of trades for the specified pair.

**Endpoint** `https://gwhbq-7aaaa-aaaar-qabya-cai.raw.icp0.io/v1/historical_trades?ticker_id=<pair_id>[&type=<buy/sell>][&limit=<limit>][&start_time=<start_time_milliseconds>][&end_time=<end_time_milliseconds>]`

E.g. https://gwhbq-7aaaa-aaaar-qabya-cai.raw.icp0.io/v1/historical_trades?ticker_id=hhaaz-2aaaa-aaaaq-aacla-cai_ryjl3-tyaaa-aaaaa-aaaba-cai&limit=10

**Parameters:**

- ticker_id: ticker_id or pair_id.
- type (optional): Specify the side of the trade - buy/sell.
- limit (optional): Number of historical trades to retrieve from time of query. 0 returns full history.
- start_time (optional): Start time (milliseconds) from which to query historical trades from.
- end_time (optional): End time (milliseconds) for historical trades query.

```json
[
    {
        "trade_id": "0000001a41fa5de863f0e453eeb08da3574564c4698e5e732e8221558f33b2b4_0",
        "price": "0.007101",
        "base_volume": "50.000000",
        "target_volume": "0.355025",
        "trade_timestamp": "1712977610871",
        "type": "buy"
    },
    {
        "trade_id": "0000003dfb5eb0cb8013ba38229e19d926827145a223f34c52a3de3187aa4ad5_0",
        "price": "0.007101",
        "base_volume": "50.000000",
        "target_volume": "0.355025",
        "trade_timestamp": "1712977610871",
        "type": "sell"
    },
    {
        "trade_id": "0000003c15f091e44a1aae7d024c7b49dfe36fac39d981ef1837994e9469bb8e_0",
        "price": "0.007100",
        "base_volume": "50.000000",
        "target_volume": "0.355000",
        "trade_timestamp": "1712973115917",
        "type": "sell"
    },
    {
        "trade_id": "00000003a096f22ac20c50d865c067ecd5b3fdf4866701b64c9f16ceabd8f463_0",
        "price": "0.007220",
        "base_volume": "415.500000",
        "target_volume": "2.999910",
        "trade_timestamp": "1712972696676",
        "type": "sell"
    },
    {
        "trade_id": "00000003a096f22ac20c50d865c067ecd5b3fdf4866701b64c9f16ceabd8f463_1",
        "price": "0.007134",
        "base_volume": "6037.200000",
        "target_volume": "43.066366",
        "trade_timestamp": "1712972696676",
        "type": "sell"
    },
    {
        "trade_id": "00000003a096f22ac20c50d865c067ecd5b3fdf4866701b64c9f16ceabd8f463_2",
        "price": "0.007133",
        "base_volume": "16387.800000",
        "target_volume": "116.900733",
        "trade_timestamp": "1712972696676",
        "type": "sell"
    },
    {
        "trade_id": "00000003a096f22ac20c50d865c067ecd5b3fdf4866701b64c9f16ceabd8f463_3",
        "price": "0.007100",
        "base_volume": "27159.400000",
        "target_volume": "192.831740",
        "trade_timestamp": "1712972696676",
        "type": "sell"
    },
    {
        "trade_id": "00000013439fd275722384342835f05389a332e6926d56529e5ee87bd2871565_0",
        "price": "0.007134",
        "base_volume": "6037.200000",
        "target_volume": "43.066366",
        "trade_timestamp": "1712972696676",
        "type": "buy"
    },
    {
        "trade_id": "0000001967c65ed00997a90ef7868522d557ec7dec65b5733b77121317d2ce08_0",
        "price": "0.007220",
        "base_volume": "415.500000",
        "target_volume": "2.999910",
        "trade_timestamp": "1712972696676",
        "type": "buy"
    },
    {
        "trade_id": "0000005f21b4ce5ae09e8c5bcc3f5e9fc48873b7ac0393cdc0316a021823d4de_0",
        "price": "0.007525",
        "base_volume": "9036.900000",
        "target_volume": "67.999961",
        "trade_timestamp": "1712971793094",
        "type": "buy"
    }
]
```