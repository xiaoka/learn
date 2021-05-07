```
 axios.post(
   url,
   {data: data},
   {
     headers: {
       'token': 'token'
     }
   }
)
.then(res => fn)
.catch(e => fn)
```

```
 axios.get(
   url,
   {
     headers: {
       'token': 'token'
     },
     params: {
       param1: string,
       param2: string
     }
   }
)
.then(res => fn)
.catch(e => fn)
```

```
  axios({
    url: `url`,
  }).then(info => fn)
```
