# 基于Nodejs搭建API服务器

### 添加CORS跨域支持


在app.js中 添加
```
app.use(function(req, res, next) {  
    res.header("Access-Control-Allow-Origin", "http://localhost:8080");  
    res.header("Access-Control-Allow-Methods","PUT,POST,GET,DELETE,OPTIONS");  
    res.header("Content-Type", "application/json;charset=utf-8"); 
    res.header("Access-Control-Allow-Headers", "Origin, X-Requested-With, Content-Type");  
    next();  
});
```

CORS跨域
`res.header("Access-Control-Allow-Origin", "*"); `
//允许那些主机访问
    所有主机  *   
    指定主机  http://www.dingai.com

//允许请求类型
`res.header("Access-Control-Allow-Methods","PUT,POST,GET,DELETE,OPTIONS"); `

//响应的类型
`res.header("Content-Type", "application/json;charset=utf-8");`

`res.header("Access-Control-Allow-Headers", "Origin, X-Requested-With, Content-Type");`





Vue 登录验证

//请求 响应 拦截处理
axios.interceptors.request.use(function (config) {
    // 在发送请求之前做些什么
    config.baseURL = "http://localhost:3000"
    if(store.state.token){
        config.headers['x-access-token'] = store.state.token;
    }
    return config;
}, function (error) {
    // 对请求错误做些什么
    return Promise.reject(error);
});
// 添加响应拦截器
axios.interceptors.response.use(function (res) {
    // 对响应数据做点什么
    // token 1001
    if(res.code == 1001){
        store.commit('save_token','');
    }
    return response;
}, function (error) {
    // 对响应错误做点什么
    return Promise.reject(error);
});


//路由处理
router.beforeEach(function(to, from, next){
  if(store.state.token||to.path =='/'){
    next();
  }else{
    next('/')
  }
})