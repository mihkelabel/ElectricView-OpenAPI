# Misc

```python
misc_controller = client.misc
```

## Class Name

`MiscController`

## Methods

* [Get Token Authenticate](../../doc/controllers/misc.md#get-token-authenticate)
* [Get BT to Actual](../../doc/controllers/misc.md#get-bt-to-actual)
* [Get Backtest](../../doc/controllers/misc.md#get-backtest)
* [Get Netted BTD Graph Values](../../doc/controllers/misc.md#get-netted-btd-graph-values)
* [Get Bot Imbalance Calculation Error](../../doc/controllers/misc.md#get-bot-imbalance-calculation-error)
* [Get Netted Hourly Data](../../doc/controllers/misc.md#get-netted-hourly-data)
* [Get Direction Change Trends](../../doc/controllers/misc.md#get-direction-change-trends)


# Get Token Authenticate

Authentication endpoint.
You need token to execute whatever next request.

```python
def get_token_authenticate(self,
                          body)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`GetTokenAuthenticateRequest`](../../doc/models/get-token-authenticate-request.md) | Body, Required | - |

## Response Type

`void`

## Example Usage

```python
body = GetTokenAuthenticateRequest()
body.username = 'Admin'
body.password = 'besobiho13'

result = misc_controller.get_token_authenticate(body)
```


# Get BT to Actual

Compare Backtest result to Bot result and to Bot + Manual (Total) result.

```python
def get_bt_to_actual(self,
                    start,
                    end,
                    bt_id,
                    plot,
                    authorization)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `start` | `string` | Query, Required | - |
| `end` | `string` | Query, Required | - |
| `bt_id` | `int` | Query, Required | - |
| `plot` | `bool` | Query, Required | - |
| `authorization` | `string` | Header, Required | - |

## Response Type

`void`

## Example Usage

```python
start = '06/01/2021 00:00:00'
end = '07/31/2022 23:59:59'
bt_id = 1001
plot = True
authorization = 'Token 2e15b4335a7e988d5f05bff5929c752757a7c1c16ac6ffc67f715a79f938f614'

result = misc_controller.get_bt_to_actual(start, end, bt_id, plot, authorization)
```


# Get Backtest

Backtest algorithm

Optional params:
lac_ma - LossAversionControl MA length
plot - Plot each BT month
save - Default False (does not save result to db)
flat - Does not return every decison
actual_trades - Count in our actual trades (default False)
last_btd_count - Select last available BTD minute
comment - BT comment

```python
def get_backtest(self,
                start,
                end,
                save,
                zone,
                bt_id,
                flat,
                comment,
                authorization)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `start` | `string` | Query, Required | - |
| `end` | `string` | Query, Required | - |
| `save` | `bool` | Query, Required | - |
| `zone` | `string` | Query, Required | - |
| `bt_id` | `int` | Query, Required | - |
| `flat` | `bool` | Query, Required | - |
| `comment` | `string` | Query, Required | - |
| `authorization` | `string` | Header, Required | - |

## Response Type

`void`

## Example Usage

```python
start = '05/19/2021 00:00:00'
end = '08/31/2022 23:59:59'
save = True
zone = 'EE'
bt_id = 1010
flat = True
comment = 'EE Balance tree 1010  Spread tree 1013 Benchmark-Run'
authorization = 'Token 2e5936965874fbedc812833105e09e710467fa5aab051cacc47e72f24a3e0f87'

result = misc_controller.get_backtest(start, end, save, zone, bt_id, flat, comment, authorization)
```


# Get Netted BTD Graph Values

This endpoint returns netted BTD values for each BTD count. (value1 + value2 + value3 + ...)

Optional params:
ma_len - for moving average.
plot - Default false. If true plots appear in the browser.

```python
def get_netted_btd_graph_values(self,
                               start,
                               end,
                               ma_len,
                               plot,
                               authorization)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `start` | `string` | Query, Required | - |
| `end` | `string` | Query, Required | - |
| `ma_len` | `int` | Query, Required | - |
| `plot` | `bool` | Query, Required | - |
| `authorization` | `string` | Header, Required | - |

## Response Type

`void`

## Example Usage

```python
start = '09/01/2022 00:00:00'
end = '09/04/2022 11:59:59'
ma_len = 180
plot = True
authorization = 'Token 2e5936965874fbedc812833105e09e710467fa5aab051cacc47e72f24a3e0f87'

result = misc_controller.get_netted_btd_graph_values(start, end, ma_len, plot, authorization)
```


# Get Bot Imbalance Calculation Error

```python
def get_bot_imbalance_calculation_error(self,
                                       start,
                                       end,
                                       authorization)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `start` | `string` | Query, Required | - |
| `end` | `string` | Query, Required | - |
| `authorization` | `string` | Header, Required | - |

## Response Type

`void`

## Example Usage

```python
start = '08/01/2022 00:00:00'
end = '08/31/2022 11:59:59'
authorization = 'Token 37d77fc95cd2db6b3c65113678cdcb7bcf5206a4b85766f2eeedb68aec8b69c1'

result = misc_controller.get_bot_imbalance_calculation_error(start, end, authorization)
```


# Get Netted Hourly Data

Return netted Hourly profit and netted Imbalance

poly_layer - on netted imbalance indicates if we made profit or loss at the given hour.

ma_len - shows moving average with selected length

```python
def get_netted_hourly_data(self,
                          start,
                          end,
                          net,
                          plot,
                          poly_layer,
                          ma_len,
                          authorization)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `start` | `string` | Query, Required | - |
| `end` | `string` | Query, Required | - |
| `net` | `bool` | Query, Required | - |
| `plot` | `bool` | Query, Required | - |
| `poly_layer` | `bool` | Query, Required | - |
| `ma_len` | `int` | Query, Required | - |
| `authorization` | `string` | Header, Required | - |

## Response Type

`void`

## Example Usage

```python
start = '06/01/2022 00:00:00'
end = '08/31/2022 23:59:59'
net = True
plot = True
poly_layer = True
ma_len = 48
authorization = 'Token 37d77fc95cd2db6b3c65113678cdcb7bcf5206a4b85766f2eeedb68aec8b69c1'

result = misc_controller.get_netted_hourly_data(start, end, net, plot, poly_layer, ma_len, authorization)
```


# Get Direction Change Trends

Returns direction changes with each direction length.

Flat - Defualt False. Returns response without trend_trades sub list.

```python
def get_direction_change_trends(self,
                               start,
                               end,
                               flat,
                               authorization)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `start` | `string` | Query, Required | - |
| `end` | `string` | Query, Required | - |
| `flat` | `bool` | Query, Required | - |
| `authorization` | `string` | Header, Required | - |

## Response Type

`void`

## Example Usage

```python
start = '08/01/2022 00:00:00'
end = '08/31/2022 23:59:59'
flat = False
authorization = 'Token 37d77fc95cd2db6b3c65113678cdcb7bcf5206a4b85766f2eeedb68aec8b69c1'

result = misc_controller.get_direction_change_trends(start, end, flat, authorization)
```

