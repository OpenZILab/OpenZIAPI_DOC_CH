[TOC]
# Cesium获取建筑信息
## 简要描述
- 获取UE场景中Cesium相关的建筑信息
## API接口
### API-Cesium获取建筑信息
#### API简要描述
- 通过点击鼠标中间获取Cesium建筑细节信息（该功能为API产品默认Pawn的功能，其他Pawn暂无此功能）
#### 请求方式
``` js
OpenZI.Call("Pawn","SetOpenMetaData", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|      参数名      | 类型 |            说明            | 备注 |
| :--------------: | :--: | :------------------------: | :--: |
| bOpenGetMetaData | bool | 是否开启获取Cesium建筑信息 |      |
#### 数据格式参考
``` js
let jsondata = {
                    "bOpenGetMetaData": true
          	}
```
#### 回调格式
``` js
let callback={
    "classDef":"Pawn",
    "funcDef":"SetOpenMetaData",
    "data":{
		"result": "success"
    }
}
```
## 备注
- 更多返回错误代码请看首页的错误代码描述