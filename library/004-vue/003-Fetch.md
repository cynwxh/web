# Fetch
```
fetch(url, options)
.then(res=>{ 
    // handle HTTP response
}, error=>{
    // handle network error
})
```

参数说明：
url：请求资源的路径 (必填)
options： 请求配置信息

| 配置项 | 数据类型 | 功能说明 | 
| ---    | ---      | --- | 
| method | String   | HTTP请求方法，默认为GET | 
| body   | String   | HTTP的请求参数 | 
| headers| Object   | HTTP的请求头，默认为{} | 
| credentials | String | 默认为omit,忽略的意思，也就是不带cookie;还有两个参数，same-origin，意思就是同源请求带cookie；include,表示无论跨域还是同源请求都会带cookie |


## 处理错误：
fetch(url, options)
.then(res=>{
	//通过判断 res.ok true|false 数据获取是否成功
	if (res.ok) {
		return res.json()
	} else {
		return Promise.reject({
			status: res.status,
			statusText: res.statusText
		})
	}
})
.then(data=>{})
.catch(err=>{})


### 发送数据
#### Post form
```
var form = document.querySelector('form')

fetch('/users', {
  method: 'POST',
  body: new FormData(form)
})
```
#### Post JSON
```
fetch('/users', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    name: 'Hubot',
    login: 'hubot',
  })
})
```
#### File upload
```
var input = document.querySelector('input[type="file"]')

var data = new FormData()
data.append('file', input.files[0])
data.append('user', 'hubot')

fetch('/avatars', {
  method: 'POST',
  body: data
})
```