####网页内容
* 减少http请求次数  
* 减少DNS查询次数(尽量在同一个域下,解析域也是耗费时间的)  
* 避免页面跳转(重新请求加载)
* 缓存Ajax
* 延迟加载
* 提前加载
* 减少DOM元素数量
* 根据域名划分内容
* 减少iframe数量
* 避免404
####CSS
* 将样式表置顶  
* 避免CSS表达式
* 用<link>代替@import 
* 避免使用Filters
####Javascript
* 将脚本置底
* 使用外部Javascirpt和CSS文件
* 精简Javascript和CSS(资源进行压缩)
* 去除重复脚本
* 减少DOM访问
* 使用智能事件处理 (减少绑定事件的数量)
####图片
* 优化图像  (把多个图标放到同一张图片中)
* 优化CSS Sprite
* 不要在HTML中缩放图片 (想用小图直接用小图)
* 使用小且可缓存的favicon.ico
####移动客户端
* 保持单个内容小于25KB
* 打包组建成符合文档
####服务器
* 使用CDN
* 添加Expires 或Cache-Control报文头
* Gzip压缩传输文件
* 配置ETags
* 尽早flush输出
* 使用GET Ajax请求
* 避免空的图片src
####Cookie   (尽量不要用)
* 减少Cookie大小
* 页面内容使用无cookie域名