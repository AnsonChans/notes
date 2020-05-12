
# JavaScript设计模式  
### 重要性  
1. 3年工作经验，面试必考  
2. 成为项目技术负责人，设计能力是必要基础  
3. 没设计，写不好代码，晋升必经之路  
### 知识点 
一. 面向对象 
1. ES6 class 
2. 三要素  
3. UML类图  

二. 设计原则（5大设计原则）  
三. 设计模式（23种设计模式）  

### 面向对象  
1.概念  
1-1. 类(模版)  
eg:   
```
  class People{  
    constructor(name,age){  
      this.name = name  
      this.age = age  
    }  
    eat(){  
      alert(${this.name} eat something)  
    }  
    speak(){  
      alert(${this.name} eat ${this.age})  
    }  
  }  
```  

1-2. 对象（实例）  
eg:  
```  
// 创建实例  
let chen = new People('chen',20)
chen.eat()  
chen.speak()  
```  

2.三要素（继承、封装、多态）  
2-1. 继承，子类继承父类   
* People是父类，公共的，不仅仅服务于Student  
* 继承可将公共方法抽离出来，提高复用，减少冗余  
eg:  
```
  父类  
  class People{  
    constructor(name,age){  
      this.name = name  
      this.age = age  
    }  
    eat(){  
      alert(${this.name} eat something)  
    }  
    speak(){  
      alert(${this.name} eat ${this.age})  
    }  
  }  
  子类  
  class Student extends People{  
    constructor(name,age,number){  
      super(name,age)  
      this.number = number  
    }  
    study(){  
      alert(${this.name} study)  
    }  
  }  
```  

2-2. 封装，数据的权限和保密  
* public 完全开放  
* protected 对子类开放  
* private 私有，对自己开放  
* es6不支持，使用typescript实现  

特点：  
* 减少耦合，不该外露的不外露  
* 利于数据/接口的权限管理  
* ES6目前不支持，一般认为_开头的属性是private  


eg:  
```
  父类  
  class People{  
    name  
    age  
    protected weight  //受保护的属性，只有自己或者子类可以访问
    constructor(name,age){  
      this.name = name  
      this.age = age  
      this.weight = 120  
    }  
    eat(){  
      alert(${this.name} eat something)  
    }  
    speak(){  
      alert(${this.name} eat ${this.age})  
    }  
  }  
  子类  
  class Student extends People{  
    number  
    private girlfriend  
    constructor(name,age,number){  
      super(name,age)  
      this.number = number  
      this.girlfriend = 'anson'
    }  
    study(){  
      alert(${this.name} study)  
    }  
  }  
```  


2-3. 多态   
* 同一接口不同实现  
* JS应用极少  
* 需要结合java等语言的接口、重写、重载等功能  

特点：  
* 保持子类的开放性和灵活性  
* 面向接口编程  
* 了解即可  

eg:  
```
  父类  
  class People{  
    constructor(name){  
      this.name = name  
    }  
    saySomething(){  
    }  
  }  
  子类  
  class A extends People{  
    constructor(name){  
      super(name)  
    }  
    saySomething(){  
      alert('I am A')  
    }  
  }  
  class B extends People{  
    constructor(name){  
      super(name)  
    }  
    saySomething(){  
      alert('I am B')    
    }  
  }  
```  


3.JS的应用举例  
* JQuery是一个class  
* $是JQuery的一个实例  

4.面向对象的意义  
* 程序执行：顺序、判断、循环————结构化  
* 面向对象————数据结构化  
* 对于计算机，结构化的才是最简单的  
* 编程应该简单&抽象  


