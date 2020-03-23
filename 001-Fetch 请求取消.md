#### 如何取消 fetch 请求
1. 创建 `AbortController` 实例
2. 实例的 `signal` 属性传给 `fetch` 方法
3. 调用 `abort` 方法，可以取消所有使用同一个 `signal` 的 `fetch` 


```javascript
function adortableFetch(request, opts) {
    const controller = new AbortController()
    const { signal } = controller

    return {
        abort: () => { controller.abort() },
        ready: fetch(request, { ...opts, signal })
    }
}

const request = adortableFetch('https://overreacted.io/page-data/app-data.json')

request.ready.then(reponse => {
    console.log('返回结果了', reponse)
}).catch(error => {
    if (error.name === 'AbortError') {
        console.log('请求取消了')
    }
})

request.abort()
```

