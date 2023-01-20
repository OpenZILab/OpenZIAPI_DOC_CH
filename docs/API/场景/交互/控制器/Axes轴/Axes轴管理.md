[TOC]

# Axes轴管理
## 简要描述
- UE场景中操作控制Axes轴管理
## API接口
### API-开启Axes工具
#### API简要描述
- 开启UE场景中操作控制Axes轴
#### 请求方式
``` js
OpenZI.Call("AxesTool","OpenAxesTool", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
| 参数名 | 类型 | 说明 | 备注 |
| :----: | :--: | :--: | :--: |
#### 数据格式参考
``` js
let jsondata = {}
```
#### 回调格式
``` js
let callback={
    "classDef":"AxesTool",
    "funcDef":"OpenAxesTool",
    "data":{
		"result": "success"
    }
}
```
### API-关闭Axes工具
#### API简要描述
- 关闭UE场景中操作控制Axes轴
#### 请求方式
``` js
OpenZI.Call("AxesTool","CloseAxesTool", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
| 参数名 | 类型 | 说明 | 备注 |
| :----: | :--: | :--: | :--: |
#### 数据格式参考
``` js
let jsondata = {}
```
#### 回调格式
``` js
let callback={
    "classDef":"AxesTool",
    "funcDef":"CloseAxesTool",
    "data":{
		"result": "success"
    }
}
```
### API-设置Axes工具选中是否选中组件
#### API简要描述
- 设置Axes工具选中是否可以选中组件
#### 请求方式
``` js
OpenZI.Call("AxesTool","SetAxesToolSelectMoth", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|  参数名   | 类型 |       说明       | 备注 |
| :-------: | :--: | :--------------: | :--: |
| component | bool | 是否可以选中组件 |      |
#### 数据格式参考
``` js
let jsondata = {
   				 "component": true
			}
```
#### 回调格式
``` js
let callback={
    "classDef":"AxesTool",
    "funcDef":"SetAxesToolSelectMoth",
    "data":{
		"result": "success"
    }
}
```
### API-设置Axes工具选中描边效果
#### API简要描述
- 设置Axes工具选中物体的描边效果（开启该功能在控制器操作中clickHighLight进行开启）
#### 请求方式
``` js
OpenZI.Call("AxesTool","SetAxesSelectionOutline", jsondata, (e) => {
    console.log(e); //成功、失败回调
})
```
#### 数据参数
|     参数名     |  类型  | 说明 | 备注 |
| :------------: | :----: | :--: | :--: |
|    strength    |  int   | 强度 |      |
|   thickness    |  int   | 厚度 |      |
| selectionColor | string | 颜色 |      |
#### 数据格式参考
``` js
let jsondata = {
             "strength": 2,
         	 "thickness": 2,
         	 "selectionColor": "1,0,0,1",
}
```
#### 回调格式
``` js
let callback={
    "classDef":"AxesTool",
    "funcDef":"SetAxesSelectionOutline",
    "data":{
		"result": "success"
    }
}
```
## 备注

- 更多返回错误代码请看首页的错误代码描述