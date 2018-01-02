# React 的学习记录

##1、ReactDOM.render()
```
ReactDOM.render(   
    <div>Hello World!!!</div>,  
    document.getElementById('root')
)  
```
1、基本语法，将模板插入html中
##2、JSX语法
```
let arr = ['小明','小红','小王']
ReactDOM.render(
    <div>
    {
        arr.map((name,i,arr) => {
            return <div key={i}>{name}</div>
        })
    }
    </div>,
    document.getElementById('root')
)
```
1. JSX是直接写在js中的html标签（不用加引号)  
2. {}代表js语法{{}}代表对象
##3、组件
```
class Hello extends Component{
    render(){
        return(
        <div>Hello World!!!!</div>
        )
    }
}
```
react可以建一个组件，Hello便是这个组件的名字。可以在当前页面也可以新建一个js文件然后引入
##4、PropTypes
```
import PropTypes from 'prop-types'

class Yesterday extends Component{
    static propTypes = {
        date:PropTypes.string
    }

    render(){
        return(	
         <div> goodby yesterday!!! {this.props.date}</div>
        )
    }
}
```
propTypes是检测传入的数据是不是预期的类型。比如string和number
##5、ref
```
class Yesterday extends Component{
    static propTypes = {
        date:PropTypes.string
    }

    _handleSumbit(){
        this.refs.contentDive.innerHTML = this.refs.myInput.value;

    }

    render(){
        return(
            <div>
                <input type="text" placeholder = "点击随意输入内容" ref = 'myInput' />
                <input type="button" value='确定' onClick={this._handleSumbit.bind(this)}/>
                <div ref = 'contentDive'></div>
            </div>
        )
    }
}
```
ref的作用基本类似于id
##6、数据的保存传递
###1、state
###2、props
##7、组件的生命周期
组件的生命周期分为3个部分
```
Mounting：已插入真实 DOM
Updating：正在被重新渲染
Unmounting：已移出真实 DOM
```
对应的函数
```
componentWillMount()    //一开始还未插入dom
componentDidMount()		//插入结束
componentWillUpdate(object nextProps, object nextState)		//将要修改
componentDidUpdate(object prevProps, object prevState) 		//修改结束
componentWillUnmount()										//dom移除
```
http://blog.csdn.net/ElinaVampire/article/details/51813677
##9、ajax
##10、其他
###1、this.props.children
