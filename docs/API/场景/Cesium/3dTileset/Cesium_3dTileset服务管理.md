[TOC]
# Cesium_3dTileset服务管理
## 简要描述
- 在场景中争对Cesium_3dTileset服务的管理
## API接口
### API-3dTileset-添加
#### API简要描述
- 在场景中添加Cesium的3dTileset服务
#### 请求方式
``` js
OpenZI.Call("Cesium3DTileset","Add", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|参数名|类型|说明|备注|
|:---: |:-:|:----:|:----: |
|id |string |3dTileset服务的唯一Id  | |
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
- 如果id存在添加会失败
``` js
let callback={
    "classDef":"Cesium3DTileset",
    "funcDef":"Add",
    "data":{
		"result": "success"
    }
}
```
### API-3dTileset-删除
#### API简要描述
- 删除场景中对应Id的Cesium的3dTileset服务
#### 请求方式
``` js
OpenZI.Call("Cesium3DTileset","Delete", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|参数名|类型|说明|备注|
|:---: |:-:|:----:|:----: |
|ids |array |需要删除的3dTileset服务的id数组  | |
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
    "classDef":"Cesium3DTileset",
    "funcDef":"Delete",
    "data":{
		"result": "success"
    }
}
```
### API-3dTileset-清除
#### API简要描述
- 清空场景中所有Cesium的3dTileset服务
#### 请求方式
``` js
OpenZI.Call("Cesium3DTileset","Clear", jsondata, (e) => {
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
    "classDef":"Cesium3DTileset",
    "funcDef":"Clear",
    "data":{
		"result": "success"
    }
}
```
### API-3dTileset-显示
#### API简要描述
- 显示场景中对应Id的Cesium的3dTileset服务
#### 请求方式
``` js
OpenZI.Call("Cesium3DTileset","Show", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|参数名|类型|说明|备注|
|:---: |:-:|:----:|:----: |
|ids |array |需要显示的3dTileset服务的id数组  | |
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
    "classDef":"Cesium3DTileset",
    "funcDef":"Show",
    "data":{
		"result": "success"
    }
}
```
### API-3dTileset-隐藏 
#### API简要描述
- 隐藏场景中对应Id的Cesium的3dTileset服务
#### 请求方式
``` js
OpenZI.Call("Cesium3DTileset","Hidden", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|参数名|类型|说明|备注|
|:---: |:-:|:----:|:----: |
|ids |array |需要隐藏的3dTileset服务的id数组  | |
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
    "classDef":"Cesium3DTileset",
    "funcDef":"Hidden",
    "data":{
		"result": "success"
    }
}
```
### API-3dTileset-更新
#### API简要描述
- 更新场景中对应id的Cesium的3dTileset服务
#### 请求方式
``` js
OpenZI.Call("Cesium3DTileset","Update", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|参数名|类型|说明|备注|
|:---: |:-:|:----:|:----: |
|id |string |3dTileset服务的唯一Id  | |
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
    "classDef":"Cesium3DTileset",
    "funcDef":"Update",
    "data":{
		"result": "success"
    }
}
```
### API-3dTileset-获取所有3DTileset
#### API简要描述
- 获取场景中所有的3DTileset
#### 请求方式
``` js
OpenZI.Call("Cesium3DTileset","GetAllCesium3DTileset", jsondata, (e) => {
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
    "classDef":"Cesium3DTileset",
    "funcDef":"GetAllCesium3DTileset",
    "data":[{
		"id": "cesium3DTileset_id",
		"sourceType": "CesiumIon",
		"url": "file:///D:/Data/OSGB/osgb/3dtiles.tileset.json",
		"ion": 96188,
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
### API-3dTileset-通过Id获取3DTileset
#### API简要描述
- 通过Id获取场景中对应的3DTileset
#### 请求方式
``` js
OpenZI.Call("Cesium3DTileset","GetAllCesium3DTileset", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|参数名|类型|说明|备注|
|:---: |:-:|:----:|:----: |
|id |string |3dTileset服务的唯一Id  | |
#### 数据格式参考
``` js
let jsondata = {
	"id": "cesium3DTileset_id",
          	}
```
#### 回调格式
- 如果id不存在更新会失败
``` js
let callback={
    "classDef":"Cesium3DTileset",
    "funcDef":"GetAllCesium3DTileset",
    "data":{
		"id": "cesium3DTileset_id",
		"sourceType": "CesiumIon",
		"url": "file:///D:/Data/OSGB/osgb/3dtiles.tileset.json",
		"ion": 96188,
		"maximumScreenSpaceError": 16.0,
		"preloadAncestors": true,
		"preloadSiblings": true,
		"forbidHoles": false,
		"maximumSimultaneousTileLoads": 20,
		"maximumCachedBytes": 256 * 1024 * 1024,
		"loadingDescendantLimit": 20,
		"enableFrustumCulling": true,
		"enableFogCulling": true
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