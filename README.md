# learn-egg

## egg初步

概念：为企业级框架和应用而生。专注于提供web开发的核心功能和一套灵活可扩展的插件机制

优点：

- egg插件机制拥有很高的扩展性，一个插件只做一件事情（比如 Nunjucks 模板封装成了 egg-view-nunjucks、MySQL 数据库封装成了 egg-mysq）。

- egg通过框架聚合这些插件，并根据自己的业务场景定制配置，这样就会降低应用的开发成本。

- [约定优于配置]，团队协作成本低。

- 基于 Koa 开发，性能优异。

- 框架稳定，测试覆盖率高。

## 启动
```
$ npm run dev
$ open localhost:7001
```

## 目录结构
```
egg-project
├── package.json
├── app.js (可选) 自定义启动时的初始化工作
├── app
|   ├── router.js 配置URL路由规则
│   ├── controller 解析用户输入，处理后返回相应的结果
│   |   └── home.js
│   ├── service (可选) 编写业务逻辑层
│   |   └── user.js
│   ├── middleware (可选) 编写中间件
│   |   └── response_time.js
│   ├── schedule (可选) 定时任务
│   |   └── my_task.js
│   ├── public (可选) 放置静态资源
│   |   └── reset.css
│   ├── view (可选) 模板文件
│   |   └── home.tpl
│   └── extend (可选) 框架扩展
│       ├── helper.js (可选)
│       ├── request.js (可选)
│       ├── response.js (可选)
│       ├── context.js (可选)
│       ├── application.js (可选)
│       └── agent.js (可选)
├── config 编写配置文件
|   ├── plugin.js 配置需要加载的插件
|   ├── config.default.js
│   ├── config.prod.js
|   ├── config.test.js (可选)
|   ├── config.local.js (可选)
|   └── config.unittest.js (可选)
└── test 单元测试
    ├── middleware
    |   └── response_time.test.js
    └── controller
        └── home.test.js
```