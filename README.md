# FlutterDemo

## SDK安装和升级
```
brew tap dart-lang/dart
brew install dart -devels
```

## 变量和常量

### 变量
- 关键字var
- 默认为null
- 强类型语言,确定了类型后不能变类型

### 常量
- 关键字 final(第一次使用时被初始化)、const(编译时常量)

### 内置类型
- Number（数字）
  * int
  * double
  * num
- String（字符串）
- Boolean（布尔）
  * bool
- List（列表）
  * var list = [1,2,3];
  * var list = new List();
  * var list = const[1, 2, 3];//不可变List
- Map（键值对）
  * Map map = {"key1": "value1"};
  * Map map = const{"key1": "value1"}; //不可变Map
  * Map map = new Map();
- Runes（符号字符）
- Symbols（标识符）

### 数值型
- 常用属性
  * isNaN,isEven,isOdd
- 常用方法
  * round、floor、ceil、toInt、toDouble、abs

### 字符串
- 创建方式
  * 单引号或双引号
  * 三引号或双引号可以创建多行字符串
  * 使用r创建原始raw字符串
- 操作
  * 插值表达式
  * 常用属性
    + length
    + isEmpty
    + isNotEmpty
  * 常用方法
    + contains
    + subString
    + starsWith
    + endWith
    + indexOf
    + lastIndexOf
    + toLowerCase
    + toUpperCase
    + trim
    + trimLeft
    + trimRight
    + split
    + replaceAll
  * 拼接
    + 单引号空格拼接
    + 双引号空格拼接
    + 单引号加号拼接
    + 双引号加号拼接

### 布尔型
- 小技巧（debugger模式下可以通过assert判断布尔值,false时会引发异常终止程序）

### List与数组
- 方法
  * length
  * add
  * insert
  * remove
  * clear
  * indexOf
  * lastIndexOf
  * sort
  * sublist
  * asMap
  * forEach
  * shuffle // 随机打乱List里元素的顺序

### Map
- 除了类似Object的方式添加和赋值外，还可以通过remove和clear方法删除和清除。

### dynamic和Object
- dart一切皆Object
- 使用dynamic告诉编译器,不用做类型检测
- 为了在运行时对类型进行检测,可以使用as 和 is 关键字

### 运算符
- 三目运算符
- ~/除法,去一个整数结果
- ..级联操作符(类似链式调用)
- as、is与is!
  * as: 判断属于某种类型
  * is: 对象具有指定的类型,为true
  * is!: 对象具有指定的类型,为false

### 异常捕获
- 抛出异常 throw Exception("")
- 捕获异常
```
try{
  // 捕获特定类型的异常
}on AuthorizationException catch(e){
  // 捕获特定类型的异常
}on Exception{
  // 捕获所有异常
}catch(e){
  // ...
}finally{
  // ...
}
```

## 函数(Function)
### main函数
```
void main => runApp(MyApp());
```

### 可选参数
```
void userSetting({int age, String name}){}
```

### 必传参数
```
void userSetting({@required int age, @required String name}){}
```

### 可选的位置参数
```
// 使用[]标记
void userSetting({int age, String name, [String interests]}){}
```

### 默认参数
```
void userSetting({int age = 21, String name = '小明'}){}
```

### 函数作为参数传递
```
void printItem(String item){
  print(item);
}

var users = ['users1', 'users2', 'users3'];
users.forEach(printItem);
```

### 函数作为变量
```
var say = (name){
  print(name);
};
say('过年了');
```

## 异步编程

### Future
```
Future<int> future = getFuture();
future.then((value)=> handleValue(value))
.catchError((error)=> handleError(error))
.whenComplete(() => handleComplete());
```

### async和await
```
steps() async{
  try{
    String step1Result1 = await step1('step1');
    String step2Result2 = await step2('step2');
    String step3Result3 = await step3('step3');
    // ...
  }catch(e){
    print(e);
  }
}
```

### 继承、接口实现和混合
- 继承(extends)
  * 子类通过override重写父类方法
  * 子类通过super调用父类方法
- 接口实现(implements)
- mixins
  * with关键字
- 执行优先级问题
  * mixins->extends->implements

### 泛型
- 抽象,减少重复代码
- 可以通过extends限制泛型的类型
