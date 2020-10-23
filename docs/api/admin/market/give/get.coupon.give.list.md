# 获取已领取优惠劵列表

#### 接口描述：
- 获取已领取优惠劵列表。

#### 请求 URL：
- `http|https://host/api/v1/coupon_give/method/get.coupon.give.list/`

#### 请求方式：
- GET
- POST

#### 是否授权：
- 需要授权

#### 业务参数：
|参数名|类型|是否必须|范围值|默认值|示例值|描述|
|:----|:---|:---:|:-----|:-----|:-----|-----|
|coupon_id |integer |否 |gt:0 | |3 |优惠劵编号 |
|type |integer |否 |in:normal,used,invalid,delete | |used |优惠劵状态，详见`附属 A` |
|account |string |否 |max:80 | |carey |账号或昵称 |
|page_no |integer |否 |gt:0 |1 |1 |页码 |
|page_size |integer |否 |gt:0 |15 |15 |每页数量 |

> 附属 A：
normal=正常状态优惠劵；used=已使用优惠劵；invalid=无效优惠劵；delete=回收站优惠劵；

#### 响应参数：
|参数名|类型|是否返回|示例值|描述|
|:-----|:-----|:---:|:-----|-----|
|status |integer |是 |200 |状态码 |
|message |string |是 |success |消息信息 |
|data |object |是 |[] |返回对象 |

|data|类型|是否返回|示例值|描述|
|:-----|:-----|:---:|:-----|-----|
|items |array |否 |[] |列表项 |
|total_result |integer |是 |102 |合计计数 |

|items|类型|是否返回|示例值|描述|
|:-----|:-----|:---:|:-----|-----|
|coupon_give_id |integer |是 |106 |优惠劵发放编号 |
|coupon_id |integer |是 |5 |优惠劵编号 |
|user_id |integer |是 |0 |账号编号 0=未领取 |
|order_id |integer |是 |0 |订单编号 0=未使用 |
|exchange_code |string |是 |bq4ZQQr7Ar |优惠劵兑换码 |
|use_time |datetime |是 |2018-05-24 16:00:00 |使用时间 |
|create_time |datetime |是 |2018-05-24 15:07:19 |创建时间 |
|get_coupon |object |是 |[] |优惠劵对象 |
|get_user |object |否 |[] |账号对象 |

|get_coupon|类型|是否返回|示例值|描述|
|:-----|:-----|:---:|:-----|-----|
|coupon_id |integer |是 |11 |优惠劵编号 |
|name |string |是 |六一快乐 |优惠劵名称 |
|description |string |是 |活动描述 |优惠劵描述 |
|guide |string |是 |//careyshop.cn |优惠劵引导地址 |
|type |integer |是 |2 |优惠劵类型，详见[「备注1」](/api/admin/market/coupon/add.coupon.item.md "「备注1」") |
|give_code |string |是 |DjEU0GtU9t |优惠劵领取码 |
|money |number |是 |100 |优惠金额 |
|quota |number |是 |1000 |限制使用金额(0则不限) |
|category |array |否 |[&quot;1&quot;,&quot;2&quot;,&quot;3&quot;] |限制商品类目 |
|exclude_category |array |否 |[&quot;5&quot;,&quot;6&quot;,&quot;7&quot;] |排除商品类目 |
|level |array |否 |[] |限制会员等级 |
|frequency |integer |是 |1 |限制领取次数(0则不限) |
|give_num |integer |是 |2000 |发放数量 |
|receive_num |integer |是 |0 |累计领取数量 |
|use_num |integer |是 |0 |累计使用数量 |
|give_begin_time |datetime |是 |2018-05-22 10:11:00 |发放开始时间 |
|give_end_time |datetime |是 |2018-06-05 00:00:00 |发放结束时间 |
|use_begin_time |datetime |是 |2018-06-01 00:00:00 |使用开始时间 |
|use_end_time |datetime |是 |2018-06-02 00:00:00 |使用结束时间 |
|status |integer |是 |1 |优惠劵状态 0=禁用 1=启用 |
|is_invalid |integer |是 |0 |优惠劵是否作废 0=正常 1=作废 |

|get_user|类型|是否返回|示例值|描述|
|:-----|:-----|:---:|:-----|-----|
|username |string |否 |carey |账号 |
|nickname |string |否 |carey |昵称 |
|head_pic |string |否 |//host/head_pic.jpg |头像 |

#### 响应示例：
```json
{
  "status": 200,
  "message": "success",
  "data": {
    "items": [
      {
        "coupon_give_id": 106,
        "coupon_id": 5,
        "user_id": 0,
        "order_id": 0,
        "exchange_code": "bq4ZQQr7Ar",
        "use_time": "",
        "create_time": "2018-05-24 15:07:19",
        "get_coupon": {
          "coupon_id": 5,
          "name": "端午节(线下)",
          "description": "",
		  "guide": "//careyshop.cn",
          "type": 1,
          "give_code": "",
          "money": 30,
          "quota": 200,
          "category": [],
          "exclude_category": [],
          "level": [],
          "frequency": 1,
          "give_num": 200,
          "receive_num": 100,
          "use_num": 0,
          "give_begin_time": "2018-05-24 02:06:00",
          "give_end_time": "2018-06-24 02:06:00",
          "use_begin_time": "2018-05-24 02:06:00",
          "use_end_time": "2018-06-24 02:06:00",
          "status": 1,
          "is_invalid": 0
        },
        "get_user": {
          "username": null,
          "nickname": null,
          "head_pic": null
        }
      },
      {
        "coupon_give_id": 105,
        "coupon_id": 5,
        "user_id": 0,
        "order_id": 0,
        "exchange_code": "4fY2JkneKs",
        "use_time": "",
        "create_time": "2018-05-24 15:07:19",
        "get_coupon": {
          "coupon_id": 5,
          "name": "端午节(线下)",
          "description": "",
		  "guide": "//careyshop.cn",
          "type": 1,
          "give_code": "",
          "money": 30,
          "quota": 200,
          "category": [],
          "exclude_category": [],
          "level": [],
          "frequency": 1,
          "give_num": 200,
          "receive_num": 100,
          "use_num": 0,
          "give_begin_time": "2018-05-24 02:06:00",
          "give_end_time": "2018-06-24 02:06:00",
          "use_begin_time": "2018-05-24 02:06:00",
          "use_end_time": "2018-06-24 02:06:00",
          "status": 1,
          "is_invalid": 0
        },
        "get_user": {
          "username": null,
          "nickname": null,
          "head_pic": null
        }
      }
    ],
    "total_result": 102
  }
}
```

#### 备注:
1. 该接口支持条件搜索，如果不带入业务参数则使用默认值。