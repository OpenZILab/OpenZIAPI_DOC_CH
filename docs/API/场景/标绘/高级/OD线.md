[TOC]
# OD线
## 简要描述
- 对UE场景中的OD线进行管理
## API接口
### API-添加OD线
#### API简要描述
- 向场景中添加OD线
#### 请求方式
``` js
OpenZI.Call("OriginDestinationLine","Add", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|参数名|类型|说明|备注|
|:---: |:-:|:----:|:----: |
|id |string |OD线唯一标识码  | |
|GISType |int | 坐标系类型|参数 0:WGS84，1:CGCS2000,2:BD09,3:GCJ02 |
|start     |string | OD线开始点位坐标 |   |
|end     |string | OD线结束点位坐标 ||
|middleHeight     |int | OD线中间点高度 |  |
|lineColor |string | 基线颜色 |  |
|lineGlow |int | OD线基线强度 | |
|lineRadius |int | OD线基线的半径比例 |                                         |
|flowColor |string | 光流颜色 | |
|flowScale |int | 光流粒子缩放 | |
|flowRate |int | 光流率 | |
#### 数据格式参考
``` js
let jsondata = {
                    "id": "OriginDestinationLine_id",
                    "GISType": 0,
                    "start": "116.38523648624017,39.92164128241577,62.0",
                    "end": "116.39425393655655,39.91212139809042,62.0",
                    "middleHeight": 20000,
                    "lineColor": "1, 0, 0, 1",
                    "lineGlow": 2,
                    "lineRadius": 1,
                    "flowColor": "0, 1, 0, 1",
                    "flowScale": 40,
                    "flowRate": 0.5
          	}
```
#### 回调格式
- 如果id存在添加会失败
``` js
let callback={
    "classDef":"OriginDestinationLine",
    "funcDef":"Add",
    "data":{
		"result": "success"
    }
}
```
### API-删除OD线
#### API简要描述
- 删除场景中对应Id的OD线
#### 请求方式
``` js
OpenZI.Call("OriginDestinationLine","Delete", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|参数名|类型|说明|备注|
|:---: |:-:|:----:|:----: |
|ids |array |需要删除的OD线的id数组 | |
#### 数据格式参考
``` js
let jsondata = {
			"ids": ["OriginDestinationLine_id"]
          	}
```
#### 回调格式
- 如果id不存在删除会失败
``` js
let callback={
    "classDef":"OriginDestinationLine",
    "funcDef":"Delete",
    "data":{
		"result": "success"
    }
}
```
### API-清除OD线
#### API简要描述
- 清空场景中所有的OD线
#### 请求方式
``` js
OpenZI.Call("OriginDestinationLine","Clear", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|参数名|类型|说明|备注|
|:---: |:-:|:----:|:----: |
|... |... |... |... |
#### 数据格式参考
``` js
let jsondata = {}
```
#### 回调格式
``` js
let callback={
    "classDef":"OriginDestinationLine",
    "funcDef":"Clear",
    "data":{
		"result": "success"
    }
}
```
### API-更新OD线
#### API简要描述
- 更新场景中对应ID的OD线
#### 请求方式
``` js
OpenZI.Call("OriginDestinationLine","Update", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
| 参数名       | 类型   | 说明               | 备注                                    |
|:---: |:-:|:----:|:----: |
|      id      | string |   OD线唯一标识码   |                                         |
|   GISType    |  int   |     坐标系类型     | 参数 0:WGS84，1:CGCS2000,2:BD09,3:GCJ02 |
|    start     | string |  OD线开始点位坐标  |                                         |
|     end      | string |  OD线结束点位坐标  |                                         |
| middleHeight |  int   |   OD线中间点高度   |                                         |
|  lineColor   | string |      基线颜色      |                                         |
|   lineGlow   |  int   |    OD线基线强度    |                                         |
|  lineRadius  |  int   | OD线基线的半径比例 |                                         |
|  flowColor   | string |      光流颜色      |                                         |
|  flowScale   |  int   |    光流粒子缩放    |                                         |
|   flowRate   |  int   |       光流率       |                                                             |
#### 数据格式参考
``` js
let jsondata = {
                    "id": "OriginDestinationLine_id",
                    "GISType": 0,
                    "start": "116.38523648624017,39.92164128241577,62.0",
                    "end": "116.39425393655655,39.91212139809042,62.0",
                    "middleHeight": 20000,
                    "lineColor": "1, 0, 0, 1",
                    "lineGlow": 2,
                    "lineRadius": 1,
                    "flowColor": "0, 0, 1, 1",
                    "flowScale": 60,
                    "flowRate": 1
          	}
```
#### 回调格式
- 如果id不存在更新会失败
``` js
let callback={
    "classDef":"OriginDestinationLine",
    "funcDef":"Update",
    "data":{
		"result": "success"
    }
}
```
## 备注
- 更多返回错误代码请看首页的错误代码描述