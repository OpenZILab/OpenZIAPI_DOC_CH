[TOC]
# Cesium影像服务管理
## 简要描述
- 在场景中争对Cesium影像服务的管理
## API接口
### API-影像-添加
#### API简要描述
- 在场景中添加Cesium的影像服务
#### 请求方式
``` js
OpenZI.Call("CesiumRasterOverlay","Add", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|参数名|类型|说明|备注|
|:---: |:-:|:----:|:----: |
|id |string |影像服务的唯一Id  | |
|terrainId |string |影像覆盖的地形id  |必须存在，不然影像不会显示 |
|type |string |影像类型  | |
|url |string |url连接，发布的服务  | |
|ionAssetID |int |ion影像服务id 0 1 2 3  | |
|ionAccessToken |string |ion影像服务token  ||
|bSpecifyZoomLevels |bool | 是否指定影像的缩放级别 | |
|layers |string | 图层名称 | |
|tileWidth |int | 影像宽度 | |
|tileHeight |int | 影像高度 | |
|minimumLevel |int | 最小层级 | |
|maximumLevel |int |最大层级  | |
|materialLayerkey |string | 覆盖材质层 |一般一个地形上面允许7个覆盖层级 |
|maximumScreenSpaceError |int |渲染当前服务的最大错误像素  | |
|maximumTextureSize |int | 光栅覆盖最大纹理大小 | |
|maximumsimultaneoustileloads |int | 可同时处于加载过程中的覆盖瓦片的最大数量| |
|subTileCacheBytes |int | 用于在内存中缓存子块的最大字节数 | |
#### 数据格式参考
``` js
let jsondata = {
				"id": "cesiumOverlay_id",
				"terrainId": "cesiumTerrain_id",
				"type": "ION",
				"url": "",
				"ionAssetID": 3,
				'ionAccessToken': "",
				"bSpecifyZoomLevels": false,
				"layers": "",
				"tileWidth": 256,
				"tileHeight": 256,
				"minimumLevel": 0,
				"maximumLevel": 14,
				"materialLayerkey": "Overlay0",
				"maximumScreenSpaceError": 2.0,
				"maximumTextureSize": 2048,
				"maximumsimultaneoustileloads": 20,
				"subTileCacheBytes": 16 * 1024 * 1024
          	}
```
#### 回调格式
- 如果id存在添加会失败
``` js
let callback={
    "classDef":"CesiumRasterOverlay",
    "funcDef":"Add",
    "data":{
		"result": "success"
    }
}
```
### API-影像-删除
#### API简要描述
- 删除场景中对应Id的Cesium的影像服务
#### 请求方式
``` js
OpenZI.Call("CesiumRasterOverlay","Delete", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|参数名|类型|说明|备注|
|:---- |:-|:-----|:----- |
|ids |array |需要删除的影像服务的id数组  | ||
#### 数据格式参考

``` js
let jsondata = {
            "ids": ["cesiumOverlay_id"]
          	}
```
#### 回调格式
- 如果id不存在删除会失败
``` js
let callback={
    "classDef":"CesiumRasterOverlay",
    "funcDef":"Delete",
    "data":{
		"result": "success"
    }
}
```
### API-影像-清除
#### API简要描述
- 清空场景中所有Cesium的影像服务
#### 请求方式
``` js
OpenZI.Call("CesiumRasterOverlay","Clear", jsondata, (e) => {
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
    "classDef":"CesiumRasterOverlay",
    "funcDef":"Clear",
    "data":{
		"result": "success"
    }
}
```
### API-影像-显示 
#### API简要描述
- 显示场景中对应Id的Cesium的影像服务
#### 请求方式
``` js
OpenZI.Call("CesiumRasterOverlay","Show", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|参数名|类型|说明|备注|
|:---: |:-:|:----:|:----: |
|ids |array |需要显示的影像服务的id数组  | |
#### 数据格式参考
``` js
let jsondata = {
            "ids": ["cesiumOverlay_id"]
          	}
```
#### 回调格式
- 如果id不存在显示会失败
``` js
let callback={
    "classDef":"CesiumRasterOverlay",
    "funcDef":"Show",
    "data":{
		"result": "success"
    }
}
```
### API-影像-隐藏    
#### API简要描述
- 隐藏场景中对应Id的Cesium的影像服务
#### 请求方式
``` js
OpenZI.Call("CesiumRasterOverlay","Hidden", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|参数名|类型|说明|备注|
|:---: |:-:|:----:|:----: |
|ids |array |需要隐藏的影像服务的id数组  | |
#### 数据格式参考
``` js
let jsondata = {
            "ids": ["cesiumOverlay_id"]
          	}
```
#### 回调格式
- 如果id不存在隐藏会失败
``` js
let callback={
    "classDef":"CesiumRasterOverlay",
    "funcDef":"Hidden",
    "data":{
		"result": "success"
    }
}
```
### API-影像-更新
#### API简要描述
- 更新场景中对应id的Cesium的影像服务
#### 请求方式
``` js
OpenZI.Call("CesiumRasterOverlay","Update", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|参数名|类型|说明|备注|
|:---: |:-:|:----:|:----: |
|id |string |影像服务的唯一Id  | |
|terrainId |string |影像覆盖的地形id  |必须存在，不然影像不会显示 |
|type |string |影像类型  | |
|url |string |url连接，发布的服务  | |
|ionAssetID |int |ion影像服务id 0 1 2 3  | |
|ionAccessToken |string |ion影像服务token  ||
|bSpecifyZoomLevels |bool | 是否指定影像的缩放级别 | |
|layers |string | 图层名称 | |
|tileWidth |int | 影像宽度 | |
|tileHeight |int | 影像高度 | |
|minimumLevel |int | 最小层级 | |
|maximumLevel |int |最大层级  | |
|materialLayerkey |string | 覆盖材质层 |一般一个地形上面允许7个覆盖层级 |
|maximumScreenSpaceError |int |渲染当前服务的最大错误像素  | |
|maximumTextureSize |int | 光栅覆盖最大纹理大小 | |
|maximumsimultaneoustileloads |int | 可同时处于加载过程中的覆盖瓦片的最大数量| |
|subTileCacheBytes |int | 用于在内存中缓存子块的最大字节数 | |
#### 数据格式参考
``` js
let jsondata = {
				"id": "cesiumOverlay_id",
				"terrainId": "cesiumTerrain_id",
				"type": "ION",
				"url": "",
				"ionAssetID": 2,
				'ionAccessToken': "",
				"bSpecifyZoomLevels": false,
				"layers": "",
				"tileWidth": 256,
				"tileHeight": 256,
				"minimumLevel": 0,
				"maximumLevel": 14,
				"materialLayerkey": "Overlay0",
				"maximumScreenSpaceError": 2.0,
				"maximumTextureSize": 2048,
				"maximumsimultaneoustileloads": 20,
				"subTileCacheBytes": 16 * 1024 * 1024
          	}
```
#### 回调格式
- 如果id不存在更新会失败
``` js
let callback={
    "classDef":"CesiumRasterOverlay",
    "funcDef":"Update",
    "data":{
		"result": "success"
    }
}
```
### API-影像-获取所有的影像
#### API简要描述
- 获取场景中所有的影像
#### 请求方式
``` js
OpenZI.Call("CesiumRasterOverlay","GetAllCesiumOverlay", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|参数名|类型|说明|备注|
|:---: |:-:|:----:|:----: |
|... |... |... |... |
#### 数据格式参考
``` js
let jsondata = {
		
          	}
```
#### 回调格式
- 返回所有影像的数据模型
``` js
let callback={
    "classDef":"CesiumRasterOverlay",
    "funcDef":"GetAllCesiumOverlay",
    "data":{
		"id": "cesiumOverlay_id",
		"terrainId": "cesiumTerrain_id",
		"type": "ION",
		"url": "",
		"ionAssetID": 2,
		'ionAccessToken': "",
		"bSpecifyZoomLevels": false,
		"layers": "",
		"tileWidth": 256,
		"tileHeight": 256,
		"minimumLevel": 0,
		"maximumLevel": 14,
		"materialLayerkey": "Overlay0",
		"maximumScreenSpaceError": 2.0,
		"maximumTextureSize": 2048,
		"maximumsimultaneoustileloads": 20,
		"subTileCacheBytes": 16 * 1024 * 1024
		"result": "success"
    }
}
```
## 服务参考
- TMS服务（地形和3Dtiels）：http://localhost:9003/model/tsUCob4zC/tileset.json
- TMS服务（影像）：http://localhost:9003/image/tms/PuFyKKcg/tilemapresource.xml
- WMS服务，如图：
![](http://117.172.238.229:5010/server/index.php?s=/api/attachment/visitFile&sign=7253f03c01af9cdcfa202af8d5b8b347)
- TMS影像服务格式，参考文件：
[meta.json](http://117.172.238.229:5010/server/index.php?s=/api/attachment/visitFile&sign=fe95f6978f16df2a40f5bb8d08ae914e "[meta.json")
- TMS地形和3Dtiels服务格，参考文件：
[tileset.json](http://117.172.238.229:5010/server/index.php?s=/api/attachment/visitFile&sign=0ab5df3d1bffef8339f8137e49986948 "[tileset.json")
## 备注
- 该系列API功能必须开启 Cesium for Unreal 插件，该插件直接在官方商城下载安装到引擎即可，为免费插件
- 更多返回错误代码请看首页的错误代码描述