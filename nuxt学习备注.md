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
### config.js
```
  head: {
    title: 'title',
    meta: [
      { charset: 'utf-8' },
      { name: 'viewport', content: 'width=device-width, initial-scale=1' },
      { hid: 'description', name: 'description', content: 'content' },
      { name: 'keywords', content: 'keywords' }
    ],
    link: [
      { rel: 'icon', type: 'image/x-icon', href: '/xxx/favicon.ico' },
      {rel: 'stylesheet', href: 'https://at.alicdn.com/t/font.css'}
    ]
  },
  css: [
    'element-ui/lib/theme-chalk/index.css',
    '~assets/css/reset.css',
    '~assets/css/border.css',
    '~assets/css/public.less',
  ],
  plugins: [
    '@/plugins/element-ui',
    '@/plugins/site' // 站点统计文件
  ],
  router: {
    base: '/xxx/',
  },
  build: {
    transpile: [/^element-ui/],
    vendor:['element-ui'],
    publicPath: '/xxx/'
  },
  server: {
    port: 1818,
    host: '0.0.0.0',
    timing: {
      total: true
    }
  }
```
