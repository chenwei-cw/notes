####1.默认绑定  
```javascript
function house(){
	console.log(this)
}
house()
```
函数作为独立函数运行时，this指向全局对象(window);   

####2.隐式绑定
```javascript
var personal = {
	name:"小明",
	house:function house(){
	console.log(this)
	}	
}
personal.house();
```
当函数放到对象里面时，函数的this指向最近的这个对象。例如：
```javascript
var personal = {
	name:"小明",
	son:{
		name:"小小明",
		house:function house(){
			console.log(this)
		}
	}
}
personal.son.house();
```
函数是被引用的。在外部声明一个函数然后用属性名引用和在对象上定义函数是一样的。因此不要纠结于函数的定义方式，根据函数的运行方式来分辨是默认绑定还是隐式绑定。例：
```javascript
var personal = {
	name:"小明",
	house:function house(){
	console.log(this)
	}	
};
function wife(myhouse){
	myhouse();	//独立运行
}
var yuefu = {
	name:"小红他爸",
	nver:wife,
	nverHouse:personal.house    //属性名引用函数
}
yuefu.nver(personal.house);
yuefu.nverHouse();
```
####3.显示绑定(call和bind方法)
call强制使this指定特定的对象
```javascript
var personal = {
	name:"小明",
	house:function house(){
	console.log(this)
	}	
};
function wife(myhouse){
	console.log(this)
	myhouse();
}
var yuefu = {
	name:"小红他爸",
	nver:wife,
	nverHouse:personal.house
}
yuefu.nver.call(personal,personal.house);
yuefu.nverHouse.call(personal); //强制使this指定特定的对象
```
call和apply差不多。懒  
bind和call的区别：call强制指定this指向的同时，函数也会执行。bind返回一个函数，函数并不会执行。
```javascript
var personal = {
	name:"小明",
	son:{
		name:"小小明",
		house:function house(){
			console.log(this)
		}
	}
}

var aaa = personal.son.house.bind(personal),
	bbb = personal.son.house;
aaa(); //显示绑定
bbb(); //默认绑定
personal.son.house();//隐式绑定
```
显示绑定后this不会改变了
####4.new 绑定

```javascript
function house(a){
	this.a = a;
}
var xiaoming = new house(1),
	xiaohong = new house(2),
	xiaobai = new house(3);
console.log(xiaoming);
console.log(xiaohong);
console.log(xiaobai);
```
