[TOC]
# POI打点管理
## 简要描述
- 对UE场景中的POI打点进行管理
## API接口
### API-添加POI点
#### API简要描述
- 在UE场景中添加POI打点
#### 请求方式
``` js
OpenZI.Call("POI","Add", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|参数名|类型|说明|备注|
|:---: |:-:|:----:|:----: |
|id |string |打点的唯一标识码  | |
|defaultStyle |string |默认样式  | 默认为："default"|
|GISType |int | 坐标系类型|参数 0:WGS84，1:CGCS2000,2:BD09,3:GCJ02 |
|coordinates     |string | 打点的地理坐标点位信息    |   |
|bAutoHeight     |bool | 是否使用自动高度 ||
|poiAlwaysVisible     |bool | 是否总是显示POI ||
|poiVisibleRange     |string | POI显示的范围 ||
|imageType     |int | 图片加载方式 |0：UE资源，1：本地文件，2：网络图片 |
|imageAddress     |string | 图片地址、网址 | |
|imageForceRefresh     |bool | 是否强制刷新图片 ||
|imageSize     |string | 图片大小 ||
|imagePivot     |string | 图片的锚点位置 ||
|imageOffset     |string | 图片的偏移 ||
|labelImageType |int |  标签图片加载方式 |0：UE资源，1：本地文件，2：网络图片 |
|labelImageAddress     |string | 标签图片地址、网址、UE资源路径 | |
|labelImageSize     |string | 标签图片大小 ||
|label     |string | 标签名 |为空不显示标签|
|labelFontName     |string | 标签所用字体的名字 ||
|labelFontSize     |int | 标签字体的大小 ||
|labelFontColor     |string | 标签的字体颜色 ||
|labelFontJustification     |int | 标签的对齐方式 |0：左对齐  1：居中 2：右对齐|
|labelBackgroundColor     |string | 标签背景颜色 ||
|labelPivot     |string | 标签的锚点位置 ||
|labelOffset     |string | 标签的偏移 ||
|labelAlwaysVisible     |bool | 是否总是显示标签 ||
|labelVisibleRange     |string | 标签的显示范围 |   |
|focusDistance     |int | 聚焦距离 |   |
#### 数据格式参考
``` js
let jsondata = {
                    "id": "poi_id",
                    "defaultStyle": "default",
                    "GISType": 0,
                    "coordinates": "116.38983567822,39.917091354324,63.499998580664",
                    "bAutoHeight":true,
                    "poiAlwaysVisible": true,
                    "poiVisibleRange": "0,2000",
                    "imageType":0,
                    "imageAddress": "",
                    "imageForceRefresh": false,
                    "imageSize": "44,45",
                    "imagePivot": "0.5,1",
                    "imageOffset": "0,0",
                    "labelImageType":0,
                    "labelImageAddress": "",
                    "labelImageSize":"44,45",
                    "label": "poi title",
                    "labelFontName": "muyao",
                    "labelFontSize": 12,
                    "labelFontColor": "1,0,0,1",
                    "labelFontJustification": 0,
                    "labelBackgroundColor": "1,1,0,0.2",
                    "labelPivot": "0,0",
                    "labelOffset": "0,-0",
                    "labelAlwaysVisible": true,
                    "labelVisibleRange": "0,2000",
                    "focusDistance":100
          	}
```
#### 回调格式
- 如果id存在添加会失败
``` js
let callback={
    "classDef":"POI",
    "funcDef":"Add",
    "data":{
		"result": "success"
    }
}
```
### API-删除POI点
#### API简要描述
- 删除UE场景中指定id的POI打点
#### 请求方式
``` js
OpenZI.Call("POI","Delete", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|参数名|类型|说明|备注|
|:---: |:-:|:----:|:----: |
|ids |array |需要删除的打点的id数组 | |
#### 数据格式参考
``` js
let jsondata = {
           "ids": ["poi_id"]
          	}
```
#### 回调格式
- 如果id不存在删除会失败
``` js
let callback={
    "classDef":"POI",
    "funcDef":"Delete",
    "data":{
		"result": "success"
    }
}
```
### API-清空POI点
#### API简要描述
- 清空UE场景中的所有POI打点
#### 请求方式
``` js
OpenZI.Call("POI","Clear", jsondata, (e) => {
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
    "classDef":"POI",
    "funcDef":"Clear",
    "data":{
		"result": "success"
    }
}
```
### API-更新POI点
#### API简要描述
- 更新UE场景中指定id的POI打点
#### 请求方式
``` js
OpenZI.Call("POI","Update", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|参数名|类型|说明|备注|
|:---: |:-:|:----:|:----: |
|id |string |打点的唯一标识码  | |
|defaultStyle |string |默认样式  | 默认为："default"|
|GISType |int | 坐标系类型|参数 0:WGS84，1:CGCS2000,2:BD09,3:GCJ02 |
|coordinates     |string | 打点的地理坐标点位信息    |   |
|bAutoHeight     |bool | 是否使用自动高度 ||
|poiAlwaysVisible     |bool | 是否总是显示POI ||
|poiVisibleRange     |string | POI显示的范围 ||
|imageType     |int | 图片加载方式 |0：UE资源，1：本地文件，2：网络图片 |
|imageAddress     |string | 图片地址、网址 | |
|imageForceRefresh     |bool | 是否强制刷新图片 ||
|imageSize     |string | 图片大小 ||
|imagePivot     |string | 图片的锚点位置 ||
|imageOffset     |string | 图片的偏移 ||
|labelImageType |int |  标签图片加载方式 |0：UE资源，1：本地文件，2：网络图片 |
|labelImageAddress     |string | 标签图片地址、网址、UE资源路径 | |
|labelImageSize     |string | 标签图片大小 ||
|label     |string | 标签名 |为空不显示标签|
|labelFontName     |string | 标签所用字体的名字 ||
|labelFontSize     |int | 标签字体的大小 ||
|labelFontColor     |string | 标签的字体颜色 ||
|labelFontJustification     |int | 标签的对齐方式 |0：左对齐  1：居中 2：右对齐|
|labelBackgroundColor     |string | 标签背景颜色 ||
|labelPivot     |string | 标签的锚点位置 ||
|labelOffset     |string | 标签的偏移 ||
|labelAlwaysVisible     |bool | 是否总是显示标签 ||
|labelVisibleRange     |string | 标签的显示范围 |   |
|focusDistance     |int | 聚焦距离 |   |
#### 数据格式参考
``` js
let jsondata = {
                      "id": "poi_id",
                    "defaultStyle": "default",
                    "GISType": 0,
                    "coordinates": "116.38983567822,39.917091354324,63.499998580664",
                    "bAutoHeight":true,
                    "poiAlwaysVisible": true,
                    "poiVisibleRange": "0,2000",
                    "imageType":0,
                    "imageAddress": "",
                    "imageForceRefresh": false,
                    "imageSize": "44,45",
                    "imagePivot": "0.5,1",
                    "imageOffset": "0,0",
                    "labelImageType":0,
                    "labelImageAddress": "",
                    "labelImageSize":"44,45",
                    "label": "poi title",
                    "labelFontName": "muyao",
                    "labelFontSize": 12,
                    "labelFontColor": "1,0,0,1",
                    "labelFontJustification": 0,
                    "labelBackgroundColor": "1,1,0,0.2",
                    "labelPivot": "0,0",
                    "labelOffset": "0,-0",
                    "labelAlwaysVisible": true,
                    "labelVisibleRange": "0,2000",
                    "focusDistance":100
          	}
```
#### 回调格式
- 如果id不存在更新会失败
``` js
let callback={
    "classDef":"POI",
    "funcDef":"Update",
    "data":{
		"result": "success"
    }
}
```
### API-聚焦POI点
#### API简要描述
- 聚焦到场景中某个打点
#### 请求方式
``` js
OpenZI.Call("POI","Focus", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|参数名|类型|说明|备注|
|:---: |:-:|:----:|:----: |
| id                     | string | 打点的唯一标识码       |                                         |
|focusDistance     |int | 聚焦距离 |   |


#### 数据格式参考
``` js
let jsondata = {
                    "id": "poi_id",
                    "foucsDistance":100
          	}
```
#### 回调格式
- 如果id不存在更新会失败
``` js
let callback={
    "classDef":"POI",
    "funcDef":"Focus",
    "data":{
		"result": "success"
    }
}
```
### API-显示POI点   
#### API简要描述
- 显示场景中已经生成的指定id的POI打点
#### 请求方式
``` js
OpenZI.Call("POI","Show", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|参数名|类型|说明|备注|
|:---: |:-:|:----:|:----: |
|ids |array |需要显示的POI点的id数组  | |
#### 数据格式参考
``` js
let jsondata = {
            "ids": ["poi_id"]
          	}
```
#### 回调格式
- 如果id不存在显示会失败
``` js
let callback={
    "classDef":"POI",
    "funcDef":"Show",
    "data":{
		"result": "success"
    }
}
```
### API-隐藏POI点
#### API简要描述
- 隐藏场景中已经生成的指定id的POI打点
#### 请求方式
``` js
OpenZI.Call("POI","Hidden", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|参数名|类型|说明|备注|
|:---: |:-:|:----:|:----: |
|ids |array |需要隐藏的POI点的id数组  | |
#### 数据格式参考
``` js
let jsondata = {
            "ids": ["poi_id"]
          	}
```
#### 回调格式
- 如果id不存在隐藏会失败
``` js
let callback={
    "classDef":"POI",
    "funcDef":"Hidden",
    "data":{
		"result": "success"
    }
}
```
## 备注
- 更多返回错误代码请看首页的错误代码描述