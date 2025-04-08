笔记管理应用前端系分

## 背景
开发一个简单的笔记管理应用：创建一个简单的笔记管理应用，能够让用户添加、查看、编辑、删除和搜索笔记，同时要求具有数据持久化和高效数据处理的功能。

## 需求分析
    1.列表模块
        搜索功能：通过input框输入关键字查询笔记，使用filter进行过滤
        笔记列表：通过循环渲染笔记列表，列表内容展示笔记标题，列表key可使用当前时间加上4位随机数
        查看笔记：点击按钮笔记模块回显当前笔记内容，并对该项进行高亮
        新增笔记：点击按钮后渲染一个新的空表单，并自动获得焦点
    2.笔记模块
        标题：input
        内容：textarea
        按钮：
            保存: 点击按钮发起保存操作，更新内存数据，并将笔记保存到localStorage
            删除：弹出二次确认框，确认后从数据中过滤该条数据，并更新页面和localStorage
## 核心技术
    核心框架：原生JavaScript
    ui框架：原生js+css
    数据持久化：
        可构造一个class用来处理笔记数据的存储，主要利用浏览器本地存储的能力，即通过localStorage单独getitem和setitem来实现。
    响应式布局：
        主要适应pc端和移动端和平板，通过媒体查询实现自适应效果，布局断点如下：
            移动端：<= 768px , 单栏布局
            平板：769-1024PX,双栏布局
            PC端：>=1025PX,双栏布局 
## 性能优化
    防抖：对笔记保存功能增加防抖

## 安全性方案
    数据验证：可增加文本长度验证
    xss防护：可对输入内容进行转义，使用textContent代替innerHTML
    数据加密：敏感信息可加盟存储