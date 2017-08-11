# seajs
[百度](https://www.baidu.com/)
1、define是一个全局方法，用来定义一个CMD模块。

2、可以define(factory)，factory可以单写一个函数，
也可以
define(function(require, exports, module) {
	// 使用require获取依赖模块的接口
    // 模块代码
    // 使用exports或者module来暴露该模块的对外接口
})

3、factory函数写法
define(function(require, exports) {
    var Vango = require('vango')
    exports.drawCircle = function () {
        var vango = new Vango(document.body, 100, 100)
        vango.circle(50, 50, 50, {
            fill: true,
            styles:{
                fillStyle:"red"
            }
        })
    }
})
也可以
define(function(require, exports, module) {
    var Vango = require('vango');
    module.exports = {
        drawCircle: function () {
            var vango = new Vango(document.body, 100, 100);
            vango.circle(50, 50, 50, {
                fill: true,
                styles:{
                    fillStyle:"red"
                }
            });
        }
    };
});
也可以先写函数，然后在依赖
exports.helloPython = helloPython;