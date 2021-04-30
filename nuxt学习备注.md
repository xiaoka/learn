### 请求方式
```
  async asyncData ({ query, error }) {
    let [request1Data, request2Data] = await Promise.all([
        axios.get('xxx'),
        axios.get('xxx')
      ])
      return {
        subjectGroup: request1Data.data.resultData,
        gradeGroup: request2Data.data.resultData
      }
  }
```
