/**
1.prototype与__proto__
  a) prototype是函数创建时创建的一个默认属性，__proto__为实例对象默认属性。
  b) 一次对象实例过程，类似以下：
      function cat(){}
      var blackCat = {};
      if(typeof cat.prototype == 'object'){
        blackCat.__proto__ = cat.prototype; // **cat.prototype为object类型，传递地址值**
      }else{
        blackCat.__proto__ = Object.prototype;// **使用Object函数prototype属性**
      }
      cat.call(blackCat);//若构造函数拥有this字，替换为实例对象blackCat

  c) 请完成练习题1系列

2.construtor
  a) constructor 属性是专门为 function 而设计的，它存在于每一个 function 的prototype 属性中。这个 constructor 保存了指向 function 的一个引用。 
      function func () {}
      console.log( func.prototype.constructor === func )//打印true
  b) 目前不需要多深入理解
  

3.call/apply(好像很鸡肋啊)
  a) 一样的作用，不一样的使用方式。(Fn是一个函数定义而不是一个实例对象)
      Fn.call(thisObj,arg1,arg2...)/Fn.apply(thisObj,[arg1,arg2...])
  b) 作用：将Fn中this指向为thisObj，再执行一次函数Fn
  c) 完成练习题2 系列
  

*/

/***********************练习题1******************************/
/** 
  var Person = function () {};
  Person.prototype.Say = function () {alert("Person say");}
  var p = new Person();
  p.Say();  //打印什么？
**/ 
//解析：原型链属性继承。



/**  
  function Person(){}
  var man = new Person();
  Person.prototype={
      name: "Tom",
      age: 20,
      saySomething: function(){
          alert("What's up?");
      }
  };
  console.log(man.name);  //打印什么？
**/
//解析：动态操作导致 Person.prototype与man.__proto__地址已经不同。



/**  
  function Person(){}
  var man = new Person();
  Person.prototype.name = "Tom";
  Person.prototype.age = 20;
  Person.prototype.saySomething = function(){alert("What's up?");};
  console.log(man.name);//打印什么？
**/
//解析：Person.prototype与man.__proto__引用地址相同，属性值操作是共享的。


/**  
  function Person(){}
  Person.prototype.name = "John";
  var man = new Person();
  Person.prototype={name:"Mike"};
  Person.prototype.name = "Tom"; 
  console.log(man.name);//打印什么？
**/



/***********************练习题2******************************/
/** 
function Cat(name){
  this.name = name;
  this.getName = function(){
    console.log(this.name);
  }
}

function Dog(name){
  this.name = name;
}

var hDog = new Dog('小猫');
Cat.call(hDog,'小狗');
hDog.getName();//打印什么
**/
//解析：call执行一次Fn,也就是执行了一次hDog.name= name,hDog.getName=function()...的过程


/** 

document.getElementsByTagName选择的dom 节点是一种类似array的array。它不能应用Array下的push,pop等方法。我们可以通过：var domNodes =  Array.prototype.slice.call(document.getElementsByTagName("*"));这样domNodes就可以应用Array下的所有方法了。

**/
