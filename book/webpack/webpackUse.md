# webpackUse
## 安装webpack  
全局安装npm install -g webpack  
安装到项目目录中npm install --save-dev webpack
## 安装依赖
`npm install --save-dev 
webpack-dev-server 
json-loader 
babel-core 
babel-loader 
babel-preset-es2015 
babel-preset-react 
react 
react-dom 
redux 
react-redux 
babel-preset-stage-1 
sass-loader 
node-sass`
## webpack.config.js 配置
`module.exports = {

     devtool: 'eval-source-map',//配置生成Source Maps，选择合适的选项
     entry: __dirname + "/js/index.js", //入口
     output: {                          //出口
         path: __dirname + "/bundle",
         filename: "guestbook.js"       //打包后的文件名
     },
 
     module: {
         loaders: [
             {
                 test: /\.json$/,
                 loader: "json-loader"
             },
             {
                 test: /\.js$/,
                 exclude: /node_modules/,
                 loader: 'babel-loader',
                 query: {
                     presets: ['es2015','react','stage-1']
                 }
             },
             {
                 test: /\.scss$/,
                 loader: 'style-loader!css-loader!sass-loader?modules=true'
             },
             {
                 test: /\.css$/,
                 use: [
                     {
                         loader: "style-loader"
                     }, {
                         loader: "css-loader",
                         options: {
                             modules: true
                         }
                     }
                 ]
             },
             {
                 test:/\.(eot|ttf|woff|woff2|svg)$/,
                 loader:'file-loader?name=fonts/[name].[ext]'
             }
         ]
     }
 }`
 ## package.json  
 `"start": "webpack-dev-server --progress --colors --hot --content-base ./bundle"`
