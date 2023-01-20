[TOC]
# Cesium地形服务管理
## 简要描述
- 在UE场景中对Cesium地形服务的管理
## API接口
### API-地形-添加
#### API简要描述
- 在场景中添加Cesium的地形服务
#### 请求方式
``` js
OpenZI.Call("CesiumTerrain","Add", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|            参数名            |  类型  |                          说明                          |       备注        |
| :--------------------------: | :----: | :----------------------------------------------------: | :---------------: |
|              id              | string |                    地形服务的唯一Id                    |                   |
|          sourceType          | string |                 服务类型 ion 获取 url                  |                   |
|             url              | string |                  url连接，发布的服务                   |                   |
|             ion              |  int   |                     ion Cesium服务                     |                   |
|   maximumScreenSpaceError    |  int   |               渲染当前服务的最大错误像素               |                   |
|       preloadAncestors       |  bool  |                  是否预先加载上级瓦片                  |                   |
|       preloadSiblings        |  bool  |                  是否预先加载同级瓦片                  |                   |
|         forbidHoles          |  bool  |       是否在子项未完成加载时取消调整回父项的瓦片       |                   |
| maximumSimultaneousTileLoads |  int   |                 一次可加载的最大瓦片数                 |                   |
|      maximumCachedBytes      |  int   |                   可缓存的最大字节数                   | 256 * 1024 * 1024 |
|    loadingDescendantLimit    |  int   | 在决定呈现自身而不是等待之前，平铺应允许加载后代的数量 |                   |
|     enableFrustumCulling     |  bool  |                    是否启用外部剔除                    |                   |
|       enableFogCulling       |  bool  |                 是否剔除被雾遮住的瓦片                 |                   |
#### 数据格式参考
``` js
let jsondata = {
                    "id": "cesiumTerrain_id",
                    "sourceType": "CesiumIon",
                    "url": "",
                    "ion": 1,
                    "maximumScreenSpaceError": 16.0,
                    "preloadAncestors": true,
                    "preloadSiblings": true,
                    "forbidHoles": false,
                    "maximumSimultaneousTileLoads": 20,
                    "maximumCachedBytes": 256 * 1024 * 1024,
                    "loadingDescendantLimit": 20,
                    "enableFrustumCulling": true,
                    "enableFogCulling": true
          	}
```
#### 回调格式
- 如果id存在添加会失败
``` js
let callback={
    "classDef":"CesiumTerrain",
    "funcDef":"Add",
    "data":{
		"result": "success"
    }
}
```
### API-地形-删除  
#### API简要描述
- 删除场景中对应Id的Cesium的地形服务
#### 请求方式
``` js
OpenZI.Call("CesiumTerrain","Delete", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|参数名|类型|说明|备注|
|:---: |:-:|:----:|:----: |
|ids |array |需要删除的地形服务的id数组  | |
#### 数据格式参考
``` js
let jsondata = {
            "ids": ["cesiumTerrain_id"]
          	}
```
#### 回调格式
- 如果id不存在删除会失败
``` js
let callback={
    "classDef":"CesiumTerrain",
    "funcDef":"Delete",
    "data":{
		"result": "success"
    }
}
```
### API-地形-清除  
#### API简要描述
- 清空场景中所有Cesium的地形服务
#### 请求方式
``` js
OpenZI.Call("CesiumTerrain","Clear", jsondata, (e) => {
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
``` js
let callback={
    "classDef":"CesiumTerrain",
    "funcDef":"Clear",
    "data":{
		"result": "success"
    }
}
```
### API-地形-显示   
#### API简要描述
- 显示场景中对应Id的Cesium的地形服务
#### 请求方式
``` js
OpenZI.Call("CesiumTerrain","Show", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|参数名|类型|说明|备注|
|:---: |:-:|:----:|:----: |
|ids |array |需要显示的地形服务的id数组  | |
#### 数据格式参考
``` js
let jsondata = {
            "ids": ["cesiumTerrain_id"]
          	}
```
#### 回调格式
- 如果id不存在显示会失败
``` js
let callback={
    "classDef":"CesiumTerrain",
    "funcDef":"Show",
    "data":{
		"result": "success"
    }
}
```
### API-地形-隐藏   
#### API简要描述
- 隐藏场景中对应Id的Cesium的地形服务
#### 请求方式
``` js
OpenZI.Call("CesiumTerrain","Hidden", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|参数名|类型|说明|备注|
|:---: |:-:|:----:|:----: |
|ids |array |需要隐藏的地形服务的id数组  | |
#### 数据格式参考
``` js
let jsondata = {
            "ids": ["cesiumTerrain_id"]
          	}
```
#### 回调格式
- 如果id不存在隐藏会失败
``` js
let callback={
    "classDef":"CesiumTerrain",
    "funcDef":"Hidden",
    "data":{
		"result": "success"
    }
}
```
### API-地形-更新  
#### API简要描述
- 更新场景中对应id的Cesium的地形服务
#### 请求方式
``` js
OpenZI.Call("CesiumTerrain","Update", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|参数名|类型|说明|备注|
|:---: |:-:|:----:|:----: |
|id |string |地形服务的唯一Id  | |
|sourceType |string |服务类型 ion 获取 url  | |
|url |string |url连接，发布的服务  | |
|ion |int |ion Cesium服务  | |
|maximumScreenSpaceError |int |渲染当前服务的最大错误像素  ||
|preloadAncestors |bool |是否预先加载上级瓦片  | |
|preloadSiblings |bool |是否预先加载同级瓦片  | |
|forbidHoles |bool |是否在子项未完成加载时取消调整回父项的瓦片  | |
|maximumSimultaneousTileLoads |int |一次可加载的最大瓦片数  | |
|maximumCachedBytes |int |可缓存的最大字节数  |256 * 1024 * 1024 |
|loadingDescendantLimit |int |在决定呈现自身而不是等待之前，平铺应允许加载后代的数量  | |
|enableFrustumCulling |bool |是否启用外部剔除  | |
|enableFogCulling |bool |是否剔除被雾遮住的瓦片  | |
#### 数据格式参考
``` js
let jsondata = {
				"id": "cesiumTerrain_id",
				"sourceType": "CesiumIon",
				"url": "",
				"ion":1,
				"maximumScreenSpaceError": 16.0,
				"preloadAncestors": true,
				"preloadSiblings": true,
				"forbidHoles": false,
				"maximumSimultaneousTileLoads": 20,
				"maximumCachedBytes": 256 * 1024 * 1024,
				"loadingDescendantLimit": 20,
				"enableFrustumCulling": true,
				"enableFogCulling": true
          	}
```
#### 回调格式
- 如果id不存在更新会失败
``` js
let callback={
    "classDef":"CesiumTerrain",
    "funcDef":"Update",
    "data":{
		"result": "success"
    }
}
```
### API-地形-获取所有地形
#### API简要描述
- 获取场景中所有的地形
#### 请求方式
``` js
OpenZI.Call("CesiumTerrain","GetAllCesiumTerrain", jsondata, (e) => {
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
- 如果id不存在更新会失败
``` js
let callback={
    "classDef":"CesiumTerrain",
    "funcDef":"GetAllCesiumTerrain",
    "data":[{
              "id": "cesiumTerrain_id",
              "sourceType": "CesiumIon",
              "url": "",
              "ion":1,
              "maximumScreenSpaceError": 16.0,
              "preloadAncestors": true,
              "preloadSiblings": true,
              "forbidHoles": false,
              "maximumSimultaneousTileLoads": 20,
              "maximumCachedBytes": 256 * 1024 * 1024,
              "loadingDescendantLimit": 20,
              "enableFrustumCulling": true,
              "enableFogCulling": true,
              "result": "success"
    }]
}
```
### API-地形-通过Id获取地形
#### API简要描述
- 通过Id获取场景中对应的地形
#### 请求方式
``` js
OpenZI.Call("CesiumTerrain","GetCesiumTerrainById", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|参数名|类型|说明|备注|
|:---: |:-:|:----:|:----: |
|id |string |地形服务的唯一Id  | |
#### 数据格式参考
``` js
let jsondata = {
	"id": "cesiumTerrain_id",
          	}
```
#### 回调格式
- 如果id不存在更新会失败
``` js
let callback={
    "classDef":"CesiumTerrain",
    "funcDef":"GetCesiumTerrainById",
    "data":{
		"id": "cesiumTerrain_id",
		"sourceType": "CesiumIon",
		"url": "",
		"ion":1,
		"maximumScreenSpaceError": 16.0,
		"preloadAncestors": true,
		"preloadSiblings": true,
		"forbidHoles": false,
		"maximumSimultaneousTileLoads": 20,
		"maximumCachedBytes": 256 * 1024 * 1024,
		"loadingDescendantLimit": 20,
		"enableFrustumCulling": true,
		"enableFogCulling": true,
		"result": "success"
    }
}
```
## 服务参考
- TMS服务（地形和3Dtiels）：http://localhost:9003/model/tsUCob4zC/tileset.json
- TMS服务（影像）：http://localhost:9003/image/tms/PuFyKKcg/tilemapresource.xml
## 备注
- 该系列API功能必须开启 Cesium for Unreal 插件，该插件直接在官方商城下载安装到引擎即可，为免费插件
- 更多返回错误代码请看首页的错误代码描述