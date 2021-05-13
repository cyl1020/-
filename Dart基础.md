### 一. Dart 入口方法 打印 注释

#### 1. 入口方法 打印

> main就是dart程序的入口，print就是dart的打印方法

- main

  ```dart
  main() {
    print('hello');
  }
  ```

- void main

  > void表示main方法没有返回值

  ```dart
  void main () {
    print('你好 dart');
  }
  ```

#### 2. 注释

- /* */ 

  > 快捷键 shift+alt+a

  ```dart
  /* 
    这是一个注释
  */
  ```

- //

  > 快捷键 ctrl+/

  ```dart
  //这是一个注释
  ```

- /// 

  > 文档注释

  ```dart
  ///这是一个注释
  ```

### 二. Dart 变量 常量

#### 1. 变量

- dart是一个强大的脚本语言，可以不预先定义变量类型，自动会类型推倒
- dart中定义变量可以通过var关键字来申明，也可以通过类型来申明

- **[注意]：**
  - var之后就不要写类型，写了类型之后就不要var，如果两者都写 `var a int = 5` 就会报错

  - dart里面有类型校验

```dart
void main() {
  // var str = '你好dart';
  // var num = 1234;
  // print(str);
  // print(num);

  // //字符串
  String str = '你好dart';
  print(str);

  // //数字类型
  int num = 1234;
  print(num);
}
```

#### 2. 变量的命名规则

- 变量名称必须由数字、字母、下划线和美元符号($)组成
- 注意：标识符开头不能是数字
- 标识符不能是保留字和关键字
- 变量的名字是区分大小写的，如age和Age是不同的变量，在实际的运用中，也建议不要用一个
- 标识符（变量名称）一定要见名思意：变量名称建议用名词，方法名称建议用动词

#### 3. 常量 

> ​    **const和final修饰符**
>

- const值不变 一开始就得赋值
- final 可以开始不赋值 但是后面只能赋值一次 final不仅有const的编译时常量的特性，最重要的它是运行时变量，并且final是惰性初始化，即在运行时第一次使用前才初始化
- 永远不改变的量，请使用final或const来修饰它，而不是使用var或其他变量类型

```dart 
main() {
  //const 常量
  // const PI = 3.14159;
  // PI = 133; //这是一个错误的写法 常量是不可以被修改的
  // print(PI);

  //final 常量
  final PI = 3.14159;
  // PI = 133; //这是一个错误的写法 常量是不可以被修改的
  print(PI);

  //const常量和final常量的区别(见上面第二点)
  // const a = new DateTime.now(); //报错
  final a = new DateTime.now(); //2020-10-12 10:22:04.218443
  print(a);
}
```

### 三. Dart 数据类型

#### 1. 常用的数据类型

- Number（数值）
  - int 
  - double
- Strings（字符串）
  - String
- Booleans（布尔）
  - bool
- List（数组）
  - 在Dart中，数组是列表对象，所以大多数人只是称它们为列表
- Maps（字典）
  - 通常来说，Map是一个键值对相关的对象，键和值可以是任何类型的对象。键只能出现一次，值可以出现多次

#### 2. 不常用的数据类型

- Runes
  - Rune是UTF-32编码的字符串，它可以通过文字转换成符号表情或者代表特定的文字
- Symbols
  - Symbol对象表示在Dart程序中声明的运算符或标识符

#### 3. 字符串类型

```dart
void main() {
  //1.定义字符串的几种方式
  //单引号和双引号都可以定义字符串，三个单引号或者三个双引号可以定义换行的字符串
  var str1 = 'this is string1';
  var str2 = "this is string2";
  var str3 = '''
  this is string3
  this is string3
  this is string3
  ''';
  var str4 = """
  this is string4
  this is string4
  this is string4
  """;

  print(str1);
  print(str2);
  print(str3);
  print(str4);

  //2.字符串的拼接
  String str5 = '你好';
  String str6 = 'dart';
  print("$str5 $str6");
  print(str5 + ' ' + str6);
}
```

#### 4. 数值类型

```dart
void main() {
  //1.int 整型
  int a = 123;
  print(a);

  //2.double 浮点型(可以将整型转换成浮点型)
  double b = 22.22; //22.22
  b = 20; //20.0
  print(b);

  //3.运算符
  //+ - * / %
  var c = a + b;
  print(c);
}
```

#### 5. 布尔类型

```dart
void main() {
  //1.bool
  bool flag1 = true;
  bool flag2 = false;
  print(flag1);
  print(flag2);

  //2.条件判断语句
  var flag = true;
  if (flag) {
    print('真');
  } else {
    print('假');
  }

  //dart ==没有类型转换
  var a = 123;
  var b = '123';
  if (a == b) {
    print('a = b');
  } else {
    print('a != b');
  }
}
```

#### 6. List集合类型

```dart
void main() {
  //1.第一种定义List的方式
  var list1 = ['aaa', 'bbb', 'ccc'];
  print(list1);
  print(list1.length);
  print(list1[0]);

  //2.第二种定义List的方式
  var list2 = new List();
  list2.add('张三'); //List的add方法
  list2.add('李四');
  list2.add('王五');
  print(list2);
  print(list2.length);
  print(list2[0]);

  //3.定义List指定类型
  var list3 = new List<String>(); //list3里面的数据的类型必须是字符串类型
  list3.add('你好');
  print(list3);
}
```

#### 7. Maps类型

```dart
void main() {
  //1.第一种定义Map的方式
  var preson1 = {
    "name": "张三",
    "age": 18,
    "work": ['程序员', '外卖员']
  };
  print(preson1);
  print(preson1["name"]);
  print(preson1["age"]);
  print(preson1["work"]);

  //2.第二种定义Map的方式
  var preson2 = new Map();
  preson2["name"] = '李四';
  preson2["age"] = 20;
  preson2["work"] = ['程序员', '外卖员'];
  print(preson2);
  print(preson2["name"]);
  print(preson2["age"]);
  print(preson2["work"]);
}
```

#### 8. 类型判断

```dart
void main() {
  //is关键词来判断类型
  var str = '1234';
  if (str is String) {
    print('是string类型');
  } else {
    print('其他类型');
  }
}
```

### 四. Dart 运算符 条件判断 类型转换

#### 1. 运算符

- 算术运算符：+  -  *  /   ~/ (取整)   %（取余）

- 关系运算符：==   !=   >   <   >=   <=

- 逻辑运算符：!   &&  ||

- 赋值运算符：

  - 基础赋值运算符  =  ??=

  -  复合赋值运算符  +=  -=  *=   /=   %=  ~/=

```dart
void main() {
  int a = 2;
  int b = 5;

  /* 算术运算符 */
  print(a + b); // 加 7
  print(a - b); // 减 -3
  print(a * b); // 乘 10
  print(a / b); // 除 0.4
  print(a % b); // 取余 2
  print(a ~/ b); // 取整 0

  print('==========================');

  /* 关系运算符 */
  print(a == b); // 判断是否相等 false
  print(a != b); // 判断是否不等 true
  print(a > b); // 判断是否大于 false
  print(a < b); // 判断是否小于 true
  print(a >= b); // 判断是否大于等于 false
  print(a <= b); // 判断是否小于等于 true

  print('==========================');

  /* 逻辑运算符 */
  // ! 取反
  // && 且 （全部为true的话值为true，否则值为false）
  // || 或 （全为false的话值为false，否则值为true）
  bool flag_1 = true;
  bool flag_2 = false;
  print(!flag_1); //false
  print(flag_1 && flag_2); //false
  print(flag_1 || flag_2); //true

  print('==========================');

  /* 赋值运算符 */
  // 基础赋值运算符   =   ??=
  int num_1 = 10;
  int num_2 = 11;
  int num_3;
  num_3 ??= 12; // 表示如果 num_3 为空的话把 12 赋值给 num_3

  // 复合赋值运算符   +=  -=  *=   /=   %=  ~/=
  int num_4 = 2;
  num_4 *= 2; // num_4 = num_4 * 2;

}
```

#### 2. 条件判断

- if else、switch case
- 三目运算符 ? :
- ??运算符

```dart
void main() {
  // if else switch case
  bool flag = true;

  if (flag) {
    print('flag == true');
  } else {
    print('flag == false');
  }

  // 判断一个人的成绩：如果大于等于60 显示及格，如果大于70 显示良好，如果大于90 显示优秀
  int score = 61;
  if (score > 90) {
    print('优秀！');
  } else if (score > 70) {
    print('良好！');
  } else if (score >= 60) {
    print('及格！');
  } else {
    print('不及格！');
  }

  // switch case
  String sex = '女';
  switch (sex) {
    case '男':
      print('性别：男');
      break;
    case '女':
      print('性别：女');
      break;
    default:
      print('性别：人妖');
  }

  // 三目运算符
  bool f = false;
  print(f ? '我是true' : '我是false');

  // ?? 运算符
  int n1;
  // int n1 = 20;
  int n2 = n1 ?? 10;  // 如果n1为空，则将10赋值给n2，否则将n1的值赋值给n2
  print('n2的值是：$n2');
}
```

#### 3. 类型转换

- Number类型转换成String类型 toString()
- String类型转成Number类型 int.parse()

```dart
void main(List<String> args) {
  /**
   * 1、Number与String类型之间的转换
   *  Number类型转换成String类型 toString()
   *  String类型转成Number类型  int.parse()
   */

  String str_1 = '123';
  print(int.parse(str_1) is int);

  print('————————————————————————————');

  String str_2 = '123.1';
  String str_3 = '123';
  print(double.parse(str_2) is double);
  print(double.parse(str_3) is double);

  print('————————————————————————————');
  try {
    String str_4 = '';
    print(double.parse(str_4) is double); // 报错
  } catch (err) {
    print(err);
  }

  print('————————————————————————————');

  int num_1 = 12;
  print(num_1.toString() is String);

  /**
   * 其他类型转换为boolean类型
   * isEmpty 判断字符串是否为空
   */

  print('————————————————————————————');
  print('————————————————————————————');

  var str_5 = '';
  if (str_5.isEmpty) {
    print('str_5为空');
  } else {
    print('str_5不为空');
  }

  var myNum;
  if (myNum == null) {
    print('空！');
  } else {
    print('非空！');
  }

  var myNum_2;
  if (myNum_2 == 0) {
    print('0！');
  } else {
    print('非0！');
  }

  var myNum_3 = 0/0;
  print('myNum_3: $myNum_3');
  if(myNum_3.isNaN) {
    print('myNum_3 is NaN');

  }
}
```

### 五. Dart 循环语句

#### 1. [补充]自增++ 和 自减--

- ++ 表示自增 1
- -- 表示自减 1
- **在赋值运算中**，如果 ++ 或 -- 写在前面，表示先运算，再赋值；如果 ++ 或 -- 写在后面，则要先赋值再运算。

```dart
void main() {

  int a = 10;
  int b = a--;
  
  print('b: $b'); // -- 在后面，先赋值再运算，所以b的值为10，a的值为9
  print('a: $a'); // -- 在后面，先赋值再运算，所以b的值为10，a的值为9

  int c = 10;
  int d = ++c;
  print('d: $d'); // ++ 在前面，先运算再赋值，所以d的值为11，c的值为11
  print('c: $c'); // ++ 在前面，先运算再赋值，所以d的值为11，c的值为11
}
```

#### 2. for循环

```dart
void main() {
  for (int i = 0; i < 10; i++) {
    print('i: $i');
  }

  print('————————————————————————————————————');

  // 1、打印出0~50所有的偶数
  for (int i = 0; i <= 50; i++) {
    if (i % 2 == 0) {
      print('0~50中的偶数：$i');
    }
  }

  print('————————————————————————————————————');

  // 2、求 1+2+3+4 +...100的和
  int sum = 0;
  for (int i = 0; i <= 100; i++) {
    sum += i;
  }
  print('1~100的和: $sum');

  print('————————————————————————————————————');

  // 3、计算5的阶乘（1*2*3*4*5）
  int sum_2 = 1;
  for (int i = 1; i <= 5; i++) {
    sum_2 *= i;
  }
  print('5的阶乘: $sum_2');

  // 4、定义一个二维数组，打印出里面的内容
  List list = [
    {
      "cate": '国内',
      "news": [
        {"title": "国内新闻1"},
        {"title": "国内新闻2"},
        {"title": "国内新闻3"}
      ]
    },
    {
      "cate": '国际',
      "news": [
        {"title": "国际新闻1"},
        {"title": "国际新闻2"},
        {"title": "国际新闻3"}
      ]
    }
  ];

  for (var i = 0; i < list.length; i++) {
    print(list[i]['cate']);
    print('--------');
    for (var j = 0; j < list[i]['news'].length; j++) {
      print(list[i]['news'][j]['title']);
    }
    print('--------');
  }
}
```

#### 3. while和do...while循环

- 语法格式

```dart
while(表达式/循环条件) {
	语句/循环体
}
```

```dart
do {
	语句/循环体
} while (表达式/循环条件)
```

- 注意：
  - 最后的分号不要忘记
  - 循环条件中使用变量需要经过初始化
  - 循环体中，应有结束循环的条件，否则会造成死循环

```dart
void main() {
  //打印1-10
  int i = 1;
  while (i < 10) {
    print('i: $i');
    i++;
  }

  // 求1+2+3+4+...+100的和
  int n = 1;
  int sum = 0;

  do {
    sum += n;
    n++;
  } while (n <= 100);
  print('1~100的和：$sum');
}
```

- **while和do...while的区别**

  第一次循环条件不成立的情况下，while不会执行语句， 而do...while会先执行一次语句，再去判断

#### 4. break和continue语句

- break语句功能：

  - 在switch语句中使流程跳出switch结构。

  - 在循环语句中使流程跳出当前循环，遇到break循环终止，后面代码也不会执行。
  - 如果在循环中已经执行了break语句，就不会执行循环体中位于break后的语句。
  - 在多层循环中，一个break语句只能向外跳出一层。
  - break可以用在switch case中 也可以用在 for 循环和 while循环中

- continue语句的功能：

  - continue只能在循环语句中使用，使本次循环结束，即跳过循环体的下面尚未执行的语句，接着进行下次的是否执行循环的判断。
  - continue可以用在 for循环 以及 while循环 中，但是不建议用在 while循环 中，不小心容易死循环。

```dart
void main(List<String> args) {

  // 打印出1~10的数，i等于4跳出循环 结果 0 1 2 3 5 6 7 8 9
  for (var i = 0; i < 10; i++) {
    if (i == 4) continue;
    print('i: $i');
  }

  // break 只能向外跳出一层
  for (var i = 0; i < 5; i++) {
    print('外层i: $i');
    for (var j = 0; j < 3; j++) {
      if (j == 2) break;
      print('里层j: $j');
    }
  }
  
  //break在switch中的应用
  var sex = "男";
  switch (sex) {
    case "男":
      print("男");
      break; //这里如果没有break会报错
    case "女":
      print("女");
      break;
    default:
  }
}
```

### 六. Dart 集合类型：List、Set、Map详解

#### 1. List

- 常用属性：
  - length 长度
  - reversed 翻转
  - isEmpty 是否为空
  - isNotEmpty 是否不为空
- 常用方法：
  - add 增加
  - addAll 拼接数组
  - indexOf 查找 传入具体值
  - remove 删除 传入具体值
  - removeAt 删除 传入索引值
  - fillRange 修改
  - insert(index,value); 指定位置插入
  - insertAll(index,list); 指定位置插入List
  - toList() 其他类型转换成List
  - join() List转换成字符串
  - split() 字符串转化成List
  - **forEach**
  - **map**
  - where() 过滤
  - any
  - every

```dart
void main() {
  List myList = ['苹果', '香蕉', '草莓', '雪梨'];

  // List属性
  print(myList);
  print(myList.length);
  print(myList.isEmpty);
  print(myList.isNotEmpty);
  print(myList.reversed); // 对列表倒序排序
  print(myList.reversed.toList());

  print('————————————————————————————————');

  // List方法

  // 增加 add addAll(需要传入一个数组)
  myList.add('桃子');
  print(myList);

  print('————————————————————————————————');

  myList.addAll(['葡萄', '西瓜']); //拼接数组
  print(myList);

  print('————————————————————————————————');

  // 查找 indexOf
  print(myList.indexOf('葡萄'));
  print(myList.indexOf('蓝莓')); // indexOf查找数据，查不到返回-1，查找返回索引值
  print('————————————————————————————————');

  // 删除 remove removeAt
  myList.remove('苹果');
  print(myList);

  myList.removeAt(2);
  print(myList);
  print('————————————————————————————————');

  // 修改 fillRange
  myList.fillRange(1, 2, 'AA');
  print(myList);
  print('————————————————————————————————');

  // 插入 insert
  myList.insert(1, 'BB');
  print(myList);

  //插入多个 insertAll
  myList.insertAll(1, ['aaa', 'bbb']);
  print(myList);

  print('—————————————— join ——————————————');
  // 连接 join
  var str = myList.join('-'); // List 转换成字符串
  print(str); // List 转换成字符串

  print('—————————————— split ——————————————');
  // 将字符串分割成数组 split
  print(str.split('-'));

  print('—————————————— for in ——————————————');
  // for in
  for (var item in myList) {
    print(item);
  }

  print('—————————————— forEach ——————————————');
  // forEach 跟 ES6 类似
  myList.forEach((item) {
    print(item);
  });

  print('—————————————— map ——————————————');
  // map
  var listMap = myList.map((item) {
    return 'N$item';
  });
  print(listMap);

  List<String> newList = listMap.toList();
  print(newList);

  print('—————————————— any ——————————————');
  // any 只要集合里面有满足条件的就返回true
  List<int> listAny = [1, 2, 3, 4, 5, 8];
  bool flagAny = listAny.any((v) {
    return v > 4; // 数组里面是否有大于4的值
  });
  print(flagAny);

  print('—————————————— where ——————————————');
  List<int> listWhere = [1, 2, 3, 4, 5, 8];
  var flagWhere = listWhere.where((v) {
    return v > 4; // 过滤出数组里面大于4的值
  });
  print(flagWhere);
  print(flagWhere.toList());

  print('—————————————— every ——————————————');
  // 每一个都满足条件返回true  否则返回false
  List<int> listEvery = [1, 2, 3, 4, 5, 8];
  bool flagEvery = listEvery.every((v) {
    return v > 2; // //每一个都满足条件返回true  否则返回false
  });
  print(flagEvery);
}
```

#### 2. Set

- Set是没有顺序且不能重复的集合，所以不能通过索引去获取值
- 常用的功能就是去除数组重复内容

```dart
void main() {
  Set mySet = new Set();
  mySet.add('苹果');
  mySet.add('香蕉');
  mySet.add('菠萝');
  mySet.add('香蕉');

  print(mySet); // {苹果, 香蕉, 菠萝}

  // 依次打印出Set的值
  mySet.forEach((item) => print(item));

  print('———————————— 实现数组去重的方法 ————————————');
  // 实现数组去重的方法
  List<String> myList = ['苹果', '苹果', '苹果', '草莓', '草莓', '草莓', '桃子'];
  print(myList);
  Set s = new Set();
  s.addAll(myList);
  print(s);
  print(s.toList());
}
```

#### 3. Map

- Map（字典）是无序的键值对
- 常用属性：
  - keys 获取所有的key值
  - values 获取所有的value值
  - isEmpty 是否为空
  - isNotEmpty 是否不为空
- 常用方法:
  - remove(key) 删除指定key的数据
  - addAll({...}) 合并映射 给映射内增加属性
  - containsValue 查看映射内的值 返回true/false
  - **forEach**
  - **map**
  - where
  - any
  - every

```dart
void main() {
  Map person = {"name": "张三", "age": 18};
  print('person: $person');

  Map p = new Map();
  p["name"] = "李四";
  p["age"] = 19;
  p["sex"] = "男";
  print('p: $p');

  // 常用属性
  print(p.keys);
  print(p.keys.toList());
  print(p.values.toList());
  print(p.isEmpty);
  print(p.isNotEmpty);

  print('————————————————————————————');

  // 常用方法
  // 增加 add addAll
  p.addAll({'job': "写代码", 'tel': 110});
  print(p);
  print('————————————————————————————');

  // 删除 remove
  p.remove("sex");
  print(p);

  print('————————————— containsValue —————————————');
  // 是否包含值
  print('是否“包含写代码”：${p.containsValue('写代码')}');

  print('————————————— forEach —————————————');
  p.forEach((key, value) {
    print('key: ${key} - value: $value');
  });
}
```

### 七. Dart 函数

#### 1. 函数的定义

- 内置方法/函数：

  ```dart
  如：print();
  ```

- 自定义方法：

  ```dart
  格式：
    返回类型  方法名称（参数1，参数2,...）{
      方法体
      return 返回值;
    }
  ```

  ```dart
  void printInfo() {
    print('我是一个自定义方法！');
  }
  
  int getNumber() {
    return 18;
  }
  
  String getString() {
    return 'this is string';
  }
  
  void main(List<String> args) {
    printInfo();
    print(getNumber());
    print(getString());
  
    // 方法的作用域
    void fn1() {
      String getA() {
        return 'A';
      }
    }
  
    //  getA(); // 报错
    fn1();
  
    print('————————————————————————————————————————');
  
    // 1、定义一个方法，求1到n的所有数的和，例如：n=60，1+2+3+...+60
    int addUp(int n) {
      int sum = 0;
      for (var i = 0; i <= n; i++) {
        sum += n;
      }
      return sum;
    }
  
    print(addUp(60));
  
    print('————————————————————————————————————————');
  
    // 2、定义一个方法然后打印用户信息
    String printUserInfo(String name, int age) {
      // 形参
      return '姓名：$name，年龄：$age';
    }
  
    print(printUserInfo('猪八戒', 9)); // 实参
  
    print('————————————————————————————————————————');
  
    // 3、定义一个带可选参数的方法
    String getUserInfo(String name, [int age]) {
      if (age != null) {
        return '姓名：$name，年龄：$age';
      } else {
        return '姓名：$name';
      }
    }
  
    print(getUserInfo('沙和尚', 10));
    print(getUserInfo('沙和尚'));
  
    print('————————————————————————————————————————');
  
    // 4、定义一个带默认参数的方法
    String getUserInfo2(String name, [String sex = '男', int age]) {
      if (age != null) {
        return '姓名：$name，性别：$sex，年龄：$age';
      } else {
        return '姓名：$name，性别：$sex，年龄：不告诉你！！！！';
      }
    }
  
    print(getUserInfo2('嫦娥', '女', 68));
    print(getUserInfo2('嫦娥', '女'));
    print(getUserInfo2('嫦娥'));
  
    print('————————————————————————————————————————');
  
    // 5、定义一个命名参数的方法(好处：不用管传参的顺序)
    String getUserInfo3(String name, {String sex = '男', int age}) {
      if (age != null) {
        return '姓名：$name，性别：$sex，年龄：$age';
      } else {
        return '姓名：$name，性别：$sex，年龄：保密 *_*';
      }
    }
  
    print(getUserInfo3('玉兔'));
    print(getUserInfo3('玉兔', sex: '女'));
    print(getUserInfo3('玉兔', sex: '女', age: 99));
  
    print('————————————————————————————————————————');
  
    // 6、实现一个把 方法 当做 参数 的方法
    fn6(fn) {
      fn();
    }
  
    fn6_1() {
      print('我是一个方法！');
    }
  
    //调用fn6这个方法，把fn6_1这个方法当做参数传入
    fn6(fn6_1);
  }
  ```

#### 2. 箭头函数

```dart
void main() {
  List<String> myList1 = ['苹果', '香蕉', '西瓜'];

  // 使用 forEach 打印出 myList 里面的数据
  myList1.forEach((value) {
    print(value);
  });

  // 箭头函数，用法1
  myList1.forEach((value) => print(value));

  // 箭头函数，用法2
  myList1.forEach((value) => {
        print(value) // 只能有一行代码，不能加分号！
      });

  List<int> myList2 = [4, 1, 2, 3, 4];

  // 修改下面 myList2 里面的数据，让数组中大于2的值乘以2
  // 写法1
  var myList2_new = myList2.map((v) {
    if (v > 2) {
      return v * 2;
    }
    return v;
  });
  print(myList2_new);

  //  写法2
  print(myList2.map((v) => v > 2 ? v * 2 : v));

  /*
  需求：
  1、定义一个方法 isEvenNumber 来判断一个数是否是偶数
  2、定义一个方法打印1-n以内的所有偶数
  */
  bool isEvenNumber(int n) {
    return n % 2 == 0 ? true : false;
  }

  void printEvenNumber(int n) {
    for (var i = 0; i <= n; i++) {
      if (isEvenNumber(i)) {
        print('偶数: $i');
      }
    }
  }

  printEvenNumber(10);
}
```

#### 3. 匿名函数

```dart
void main() {
  // 匿名函数
  var printNumber = (int n) {
    print(n);
  };

  printNumber(999);

  // 自执行方法(类似于js的立即执行函数)
  (() {
    print('我是一个自执行方法！');
  })();
    
  //这也是自执行方法的一种写法
  (){
    print(2);
  }();

  // 方法的递归
  // 使用方法递归，求1~100的和
  var sum = 0;
  fn(int n) {
    sum += n;
    n == 0 ? false : fn(n - 1);
  }

  fn(100);
  print('sum: $sum');
}
```

#### 4. 闭包

- 全局变量特点： 全局变量会常驻内存、全局变量会污染全局。
- 局部变量的特点： 不常驻内存会被垃圾机制回收、不会污染全局。
- 想实现的功能：
  1、常驻内存
  2、不污染全局
  于是就产生了闭包，闭包可以实现这个功能。
- 闭包：函数嵌套函数，内部函数会调用外部函数的变量或参数，变量或参数不会被系统回收(不会释放内存)
- 闭包的写法：函数嵌套函数，并 return 里面的函数，这样就形成了闭包。

```dart
void main() {
// 闭包
  closureFn() {
    int localVariableNumber = 888; // 该变量常驻内存，又不会污染全局
    return () {
      localVariableNumber++;
      print(localVariableNumber);
    };
  }

  // 使用闭包
  var fn = closureFn();
  fn(); // 889
  fn(); // 890
  fn(); // 891
}
```

### 八. Dart 类

#### 1. 类的介绍

- 面向对象编程(OOP)的三个基本特征：**封装、继承、多态**。
  - 封装：封装是对象和类概念的主要特性。封装，把客观事物封装成抽象的类，并且把自己的部分属性和方法提供给其他对象调用, 而一部分属性和方法则隐藏。
  - 继承：面向对象编程 (OOP) 语言的一个主要功能就是“继承”。继承是指这样一种能力：它可以使用现有类的功能，并在无需重新编写原来的类的情况下对这些功能进行扩展。
  - 多态：允许将子类类型的指针赋值给父类类型的指针, 同一个函数调用会有不同的执行效果。
- Dart 所有的东西都是对象，所有的对象都继承自 Object 类。
- Dart 是一门使用类和单继承的面向对象语言，所有的对象都是类的实例，并且所有的类都是 Object 的子类。
- 一个类通常由**属性**和**方法**组成。

#### 2. 类的定义

Dart 是一门使用类和单继承的面向对象语言，所有的对象都是类的实例，并且所有的类都是Object的子类。

```dart
// 创建一个自定义的类 Person
class Person {
  String name = '张三';
  int age = 18;
  String _job;  // 在变量名前面加下划线，表示私有属性
  //注意：想要实现私有属性或者私有方法，必须将该类单独抽离到一个文件中，这样实例化对象就不能直接访问私有属性和私有方法了，但是实例化对象可以间接的访问（通过共有的方法来访问）。
  
  void printPersonInfo(){
    print('name: $name，age: $age');
  }

  void setAge (age) {
    this.age = age;
  }
}

void main(List<String> args) {

  // 实例化Person类
  Person p1 = new Person();
  p1.printPersonInfo();
  p1.setAge(99);
  p1.printPersonInfo();
  
}
```

#### 3. 自定义类的构造函数

```dart
// 创建一个自定义的类 Person
class Person1 {
  String name;
  int age;

  // 默认的构造函数，在类实例化时自执行
  Person1(String name, int age) {
    this.name = name;
    this.age = age;
  }

  // 构造函数简写
  // Person(this.name, this.age);

  void printPersonInfo() {
    print('name: $name，age: $age');
  }
}

// Dart里面的构造函数可以写多个
// 命名构造函数
class Person2 {
  String name;
  int age;

  // 构造函数简写
  Person2(this.name, this.age);

  Person2.rename() {
    print('我是命名构造函数!');
  }

  void printPersonInfo() {
    print('name: $name，age: $age');
  }
}

void main(List<String> args) {
  // 实例化 Person1 类
  Person1 p1 = new Person1('李四', 19);
  p1.printPersonInfo();

  print('————————————————————————————');

   // 实例化 Person2 类
  Person2 p2 = new Person2('王五', 20);  // 实例化类的时调用的是默认构造函数
  p2.printPersonInfo();

  Person2 p2_2 = new Person2.rename(); //输出：我是命名构造函数!
  p2_2.printPersonInfo();
}
```

#### 4. 自定义的类单独抽离成模块

```dart
import 'moduls/Person.dart';
import 'moduls/Animal.dart' as A;

void main(List<String> args) {
  // 调用其他文件的类
  Person p = new Person('孙悟空', 777);
  p.printPersonInfo();

  print('————————————————————————————');

  A.Animal a = new A.Animal('奶牛', 5);
  a.printInfo();
  a.execRun();
}
```

#### 5. 类的getter和setter

```dart
class Rect {
  num height;
  num width;
  Rect(this.height, this.width);
  getArea() {
    return this.height * this.width;
  }

  // getter
  // 获取矩形周长
  get perimeter {
    return this.height * 2 + this.width * 2;
  }

  // setter
  // 设置矩形高度
  set rectHeight(num height) {
    this.height = height;
  }
}

void main(List<String> args) {
  Rect r = new Rect(10, 20);
  print('矩形面积：${r.getArea()}');

  print('————————————————————');

  print('矩形周长：${r.perimeter}');  // getter用法 调用直接通过访问属性的方式访问perimeter

  // 设置矩形的高度
  r.rectHeight = 6;  // setter用法
  print('重新设置过高度之后的矩形周长：${r.perimeter}');  
}
```

#### 6. 类的初始化

```dart
class Rect {
  int height;
  int width;

  // 类的属性初始化写法
  Rect(): height = 2, width = 3 {
    print('height初始化的值：$height, height初始化的值：$width');
  }

  getArea() {
    return this.height * this.width;
  }
}

void main(List<String> args) {
  Rect r  = new Rect();
  print(r.getArea());
}
```

#### 7. 静态类和静态方法

- 1、使用 static 关键字定义静态成员和方法。**使用类名称直接访问静态属性和静态方法**。
- 2、静态方法不能访问非静态属性，非静态方法可以访问静态成员。

```dart
class Person {
 static String name = '张三';
 int age = 18;

 static void printInfo() {
   print('我是一个静态方法');
   print(name);
   // print(this.age);  // 报错，静态方法不能访问非静态属性
 }

 getInfo() {
   print(Person.name);
   print(this.age); // 非静态方法可以访问静态成员

   printInfo(); // 调用静态方法
 }
}

void main(List<String> args) {
 Person p = new Person();
 p.getInfo();
 Person.printInfo(); // 调用静态方法，不用new(实例化)，直接调用
}
```

#### 8. 对象操作符

- ? 条件操作符
- as 类型转换
- is 类型判断
- .. 级联操作

```dart
class Person {
 String name;
 num age;

 Person(this.name, this.age);

 void printInfo() {
   print('name: $name, age: $age');
 }
}

void main(List<String> args) {
 Person p = new Person('诸葛亮', 67);

 // ? 条件操作
 p?.printInfo();

 print('————————————————————————————————————');

 // is 类型判断
 if (p is Person) {
   p.name = '李四';
 }

 p.printInfo();

 print(p is Object);

 print('————————————————————————————————————');

 // as 类型转换
 var p2;
 p2 = '';
 p2 = new Person('唐三藏', 100);
 p2.printInfo(); // IDE不会自动推断出该方法名
 (p2 as Person).printInfo(); // 类型转换后，IDE会智能提示

 print('————————————————————————————————————');

 // .. 级联操作
 Person p3 = new Person('沙和尚', 99);
 p3.printInfo();

 p3.name = '沙和尚牛逼';
 p3.age = 111;
 p3.printInfo();

 // 等同于
 p3
   ..name = '沙和尚无敌'
   ..age = 222
   ..printInfo();
}
```

#### 9. 类的继承

- 面向对象的三大特性：**封装 、继承、多态**
- Dart中的类的继承：
  - 1、子类使用extends关键字来继承父类。
  - 2、子类会继承父类里面可见的属性和方法，但是不会继承构造函数。
  - 3、子类能覆写父类的方法getter和setter。

```dart
class Person1 {
  String name = '张三';
  num age = 18;
  void printInfo() {
    print('name: $name, age: $age');
  }
}

// Men1 继承 Person1
class Men1 extends Person1 {}

// ——————————————————————————————————————————————————

class Person2 {
  String name;
  num age;

  Person2(this.name, this.age);

  void printInfo() {
    print('name: $name, age: $age');
  }
}

// Men2 继承 Person2
class Men2 extends Person2 {
  Men2(String name, num age) : super(name, age) {}
}

// ——————————————————————————————————————————————————
// Men3 继承 Person2
class Men3 extends Person2 {
  String sex;
  Men3(String name, num age, String sex) : super(name, age) {
    this.sex = sex;
  }

  printUserInfo() {
    print('name: $name, age: $age, 性别: $sex');
  }
}

// ——————————————————————————————————————————————————
class Person4 {
  String name;
  num age;
  Person4(this.name, this.age);
  Person4.xxx(this.name, this.age);
  void printInfo() {
    print("姓名：${this.name}，年龄：${this.age}");
  }
}

class Men4 extends Person4 {
  String sex;
  Men4(String name, num age, String sex) : super.xxx(name, age) { //调用父类的xxx方法
    this.sex = sex;
  }
  showUserInfo() {
    print("姓名：${this.name}，年龄：${this.age}，性别：${this.sex}");
  }
}

void main(List<String> args) {
  Men1 m = new Men1();
  m.printInfo();

  print('——————————————————————————————————————————');

  Men2 m2 = new Men2('李白', 89);
  m2.printInfo();

  print('——————————————————————————————————————————');
  Men3 m3 = new Men3('李清照', 22, '女');
  m3.printUserInfo();

  print('——————————————————————————————————————————');
  Men4 m4 = new Men4('辛弃疾', 30, '男');
  m4.showUserInfo();
}
```

#### 10. 子类覆写父类的方法

覆写父类的方法，建议在方法名前面加上@override，有助于辨识，也可以不加。

子类使用 `super.父类的方法` 来调用父类的方法。也可以使用 `this.父类的方法` 来调用父类的方法。

```dart
class Person {
  String name;
  num age;
  Person(this.name, this.age);
  void printInfo() {
    print("${this.name}，${this.age}");
  }

  work() {
    print("${this.name}在工作...");
  }
}

class Men extends Person {
  Men(String name, num age) : super(name, age);

  run() {
    print('子类的run()方法！');
    super.work();  // 子类里面调用父类的方法
  }

  // 覆写父类的方法
  @override // 可以写也可以不写，建议加上
  void printInfo() {
    print("姓名：${this.name}，年龄：${this.age}");
  }

  @override
  work() {
    print("${this.name}的工作是写代码");
  }
}

void main(List<String> args) {
  Men m = new Men('程咬金', 88);
  m.printInfo();
  m.work();
  m.run(); 
}
```

#### 11. 抽象类

- Dart抽象类主要用于定义标准，子类可以继承抽象类，也可以实现抽象类接口。
  - 1、抽象类通过 abstract 关键字来定义。
  - 2、抽象方法不能用 abstract 声明，Dart中没有方法体的方法我们称为抽象方法。
  - 3、如果子类继承抽象类必须得实现里面的抽象方法。
  - 4、如果把抽象类当做接口实现的话必须得实现抽象类里面定义的所有属性和方法。
  - 5、抽象类不能被实例化，只有继承它的子类可以。
- extends抽象类 和 implements 的区别：
  - 1、如果要复用抽象类里面的方法，并且要用抽象方法约束自类的话我们就用 extends 继承抽象类。
  - 2、如果只是把抽象类当做标准的话我们就用 implements 实现抽象类

```dart
// 案例：定义一个Animal 类要求它的子类必须包含eat和run方法
abstract class Animal {
  eat(); // 抽象方法
  run(); // 抽象方法
  printInfo() {
    print('我是抽象类里面的普通方法');
  }
}

class Dog extends Animal {
  @override
  eat() {
    // TODO: implement eat
    print('Dog eat...');
  }

  @override
  run() {
    // TODO: implement run
    print('Dog run...');
  }
}

class Cat extends Animal {
  @override
  eat() {
    // TODO: implement eat
    print('Cat eat...');
  }

  @override
  run() {
    // TODO: implement run
    print('Cat run...');
  }
}

void main(List<String> args) {
  Dog d = new Dog();
  d.eat();
  d.run();
  d.printInfo();

  print('——————————————————————');

  Cat c = new Cat();
  c.eat();
  c.run();
  c.printInfo();

  print('——————————————————————');
  // Animal a = new Animal(); // 报错，抽象不能被实例化！！
}
```

#### 12. 多态

- 允许将子类类型的指针赋值给父类类型的指针，同一个函数调用会有不同的执行效果。
- 子类的实例赋值给父类的引用。
- 多态就是父类定义一个方法不去实现，让继承他的子类去实现，每个子类有不同的表现。

```dart
abstract class Animal {
 eat(); //抽象方法
}

class Dog extends Animal {
 @override
 eat() {
   print('Dog eat...');
 }

 run() {
   print('Dog run...');
 }
}

class Cat extends Animal {
 @override
 eat() {
   print('Cat eat...');
 }

 run() {
   print('Cat run...');
 }
}

void main(List<String> args) {
 Animal d = new Dog();
 Animal c = new Cat();

 d.eat();
 c.eat();
}
```

### 九. Dart 接口

#### 1. 接口的定义

- 和Java一样，Dart也有接口，但是和Java还是有区别的。
- Dart的接口没有interface关键字来定义，而是普通类或抽象类都可以作为接口被实现。
- 同样使用implements关键字进行实现。
- 但是Dart的接口有点奇怪，如果实现的类是普通类，会将普通类和抽象中的属性的方法全部需要覆写一遍。
- 抽象类可以定义抽象方法，普通类不可以，所以一般如果要实现像Java接口那样的方式，一般会使用抽象类。
- 建议使用抽象类定义接口。

```dart
// 案例：定义一个数据库接口 DB ，使得 MySQL MongoDB 等数据库可以使用这个接口
abstract class DB { //接口就是约定/规范
 String uri; //数据库的连接地址
 add(String data);
 save(String data);
 delete(int id);
}

class MySQL implements DB {
 @override
 String uri;

 MySQL(this.uri); //构造函数

 @override
 add(String data) {
   // TODO: implement add
   print('MySQL Add $data');
 }

 @override
 save(String data) {
   // TODO: implement save
   return null;
 }

 @override
 delete(int id) {
   // TODO: implement delete
   return null;
 }

}

class MongoDB implements DB {
 @override
 String uri;

 MongoDB(this.uri);

 @override
 add(String data) {
   // TODO: implement add
   print('MongoDB Add $data');
 }

 @override
 save(String data) {
   // TODO: implement save
   return null;
 }

 @override
 delete(int id) {
   // TODO: implement delete
   return null;
 }

}

void main(List<String> args) {

 MongoDB mongoDB = new MongoDB('https://xpoet.cn/');
 
 mongoDB.add('😺');
}
```

#### 2. 接口模块化

将不同的接口抽离成单个文件，需要时通过 import 导入。

```dart
import './interfaces/MySQL.dart';

void main(List<String> args) {

  MySQL mySQL = new MySQL('https://github.com/XPoet');
  mySQL.uri = 'i@xpoet.cn';
  mySQL.add('new data');
}
```

#### 3. 一个类实现多个接口

```dart
abstract class A {
  String xxx;
  printA();
}

abstract class B {
  printB();
}

// class C 实现 A, B 两个接口
class C implements A, B {
  @override
  String xxx;

  @override
  printA() {
    // TODO: implement printA
    return null;
  }

  @override
  printB() {
    // TODO: implement printB
    return null;
  }
}

void main(List<String> args) {
  C c = new C();
  c.printA();
  c.printB();
}
```

#### 4. Mixins

- Mixins 的中文意思是混入，就是在类中混入其他功能
- 在 Dart 中可以使用 Mixins 实现类似多继承的功能
- 因为 Mixins 使用的条件，随着 Dart 版本一直在变，这里讲的是 Dart2.x 中使用 Mixins 的条件：
  - 1、作为 Mixins 的类只能继承自 Object，不能继承其他类
  - 2、作为 Mixins 的类不能有构造函数
  - 3、一个类可以 Mixins 多个 Mixins 类
  - 4、Mixins 绝不是继承，也不是接口，而是一种全新的特性
  - 5、Mixins 的实例类型就是其超类的子类型

```dart
class A {
  String info = 'this is A';
  void printA() {
    print('A');
  }

  void run() {
    print('class A run');
  }
}

class B {
  void printB() {
    print('B');
  }

  void run() {
    print('class B run');
  }
}

class Person {
  String name;
  num age;
  Person(this.name, this.age);
  void printInfo() {
    print('姓名：$name，年龄：$age');
  }

  void run() {
    print('class Person run');
  }
}

class C with A, B {}

// class C2 继承 Person，混入 B, A
class C2 extends Person with B, A {
  C2(String name, num age) : super(name, age);
}

void main() {
  C c = new C();
  c.printA();
  print(c.info);
  c.printB();

  print('————————————————————————————————');

  C2 c2 = new C2('赵六', 16);
  c2.printInfo();
  print(c2.info);
  c2.run();  // class A run （执行的 with 后面最后一个类的 run() 方法）

  print('————————————————————————————————');
  // mixins的实例类型
  var c3 = new C2('赵七', 16);
  print(c3 is C2);  // true
  print(c3 is A);   // true
  print(c3 is B);   // true
  print(c3 is Person);  // true
}
```

### 十. Dart 泛型

- 泛型是指在定义函数、接口或类的时候，不预先指定具体的类型，而在使用的时候再指定类型的一种特性。
- 通俗理解：泛型就是解决类、接口、方法的复用性，以及对不特定数据类型的支持（类型校验）。

#### 1. 泛型方法

```dart
// 不使用泛型存在的问题
// 1、只能返回 String 类型数据
String getData1(String data) {
  return data;
}

// 2、只能返回 int 类型数据
int getData2(int data) {
  return data;
}

// 3、能返回 String 或 int 类型数据，不指定类型可以解决这个问题，但放弃了类型检查
getData3(data) {
  return data;
}

// 修改：使用泛型，传入什么类型，就返回什么类型。T 表示泛型
getData<T>(T data) {
  return data;
}

void main(List<String> args) {
  print(getData<int>(10));
  print(getData<String>('this is string'));
}
```

#### 2. 泛型类

Dart 泛型类的用法，如下案例：

```dart
// 案例：把下面类转换成泛型类，要求 List 里面可以增加 int 类型的数据，也可以增加 String 类型的数据。
// 但是每次调用增加的类型要统一。
class PrintList1 {
  List list = new List<int>();
  void add(int value) {
    this.list.add(value);
  }

  void printInfo() {
    for (var i = 0; i < this.list.length; i++) {
      print(this.list[i]);
    }
  }
}

// 泛型类
class PrintList2<T> {
  List list = new List<T>();
  void add(T value) {
    this.list.add(value);
  }

  void printInfo() {
    for (var i = 0; i < this.list.length; i++) {
      print(this.list[i]);
    }
  }
}

void main(List<String> args) {
  PrintList1 printList1 = new PrintList1();
  printList1.add(1);
  printList1.add(2);
  printList1.add(3);
  printList1.printInfo();

  print('——————————————————————————————————————————');

  // 使用泛型类，传入 String 类型
  PrintList2 printList2 = new PrintList2<String>();
  printList2.add('A');
  printList2.add('B');
  printList2.add('C');
  printList2.printInfo();

  print('——————————————————————————————————————————');

  // 使用泛型类，传入 int 类型
  PrintList2 printList3 = new PrintList2<int>();
  printList3.add(2);
  printList3.add(4);
  printList3.add(6);
  printList3.printInfo();
}
```

#### 3. 泛型接口

Dart 泛型接口的用法，参考如下案例：

```dart
// 案例：实现数据缓存的功能：有文件缓存、和内存缓存。内存缓存和文件缓存按照接口约束实现。
// 1、定义一个泛型接口，约束实现它的子类必须有 getByKey(key) 和 setByKey(key,value)
// 2、要求 setByKey 的时候的 value 的类型和实例化子类的时候指定的类型一致

abstract class Cache<T> {
  getByKey(String key);
  void setByKey(String key, T value) {}
}

class FileCache<T> implements Cache<T> {
  @override
  getByKey(String key) {
    // TODO: implement getByKey
    return null;
  }

  @override
  void setByKey(String key, T value) {
    // TODO: implement setByKey
    print('File cache: 写入{$key:$value}到文件中。');
  }
}

class MemoryCache<T> implements Cache<T> {
  @override
  getByKey(String key) {
    // TODO: implement getByKey
    return null;
  }

  @override
  void setByKey(String key, T value) {
    // TODO: implement setByKey
    print('Memory cache: 写入{$key:$value}到内存中。');
  }
}

void main(List<String> args) {
  FileCache fileCache = new FileCache<int>();
  fileCache.setByKey('age', 18); // File cache: 写入{age:18}到文件中。

  print('——————————————————————————————————————————');

  MemoryCache memoryCache = new MemoryCache<Map>();
  memoryCache.setByKey('person', {
    'name': '张三',
    'age': 20
  }); // Memory cache: 写入{person:{name: 张三, age: 20}}到内存中。
}
```

### 十一. Dart 库

#### 1. Dart 库的使用介绍

前面讲解 Dart 基础知识的时候大多数是在一个文件里面编写 Dart 代码的，但实际开发中不可能这么写，模块化很重要，这就需要使用到**库**的概念。

- 在 Dart 中，库的使用时通过 import 关键字引入的。

- library 指令可以创建一个库，每个 Dart 文件都是一个库，即使没有使用 library 指令来指定。

- Dart 中的库主要有三种：

  - 1、我们自定义的库
    `import 'lib/xxx.dart';`

  - 2、系统内置库
    `import 'dart:math';`
    `import 'dart:io';`
    `import 'dart:convert';`

  - 3、Pub 包管理系统中的库
    `https://pub.dev/packages`
    `https://pub.flutter-io.cn/packages`
    `https://pub.dartlang.org/flutter/`

    ```
    使用第三方库的方法：
    ```

    - 1、需要在自己项目根目录新建一个 pubspec.yaml
    - 2、在 pubspec.yaml 文件 然后配置名称 、描述、依赖等信息
    - 3、然后运行 pub get 获取包下载到本地
    - 4、项目中引入库，例如：`import 'package:http/http.dart' as http;`
    - 5、查看第三方库的官方文档使用。

```dart
// 导入自己的库
import 'library/Animal.dart';

// 导入内置的库
import 'dart:math';

// 冲突解决
// 当引入两个库中有相同名称标识符的时候，如果是java通常我们通过写上完整的包名路径来指定使用的具体标识符，甚至不用import都可以。
// 但是Dart里面是必须import的。当冲突的时候，可以使用as关键字来指定库的前缀。
// 如下例子所示：
import 'library2/Animal.dart' as l2;

void main(List<String> args) {

  // 使用导入的自己的库
  Animal animal = new Animal('pig', 2);
  animal.printInfo();

  // 冲突解决，取别名
  l2.Animal animal2 = new l2.Animal('dog', 5);
  animal2.printInfo();

  print('——————————————————————————————————');

  // 使用导入的内置的库的方法
  print('min: ${min(1, 11)}');
  print('max: ${max(1, 11)}');
}
```

**案例：使用 Dart 内置库实现请求数据的功能**

```dart
import 'dart:io';
import 'dart:convert';

// API接口：http://news-at.zhihu.com/api/3/stories/latest
getDataFromZhihuAPI() async {
  // 1、创建 HttpClient 对象
  HttpClient httpClient = new HttpClient();

  // 2、创建 URI 对象
  Uri uri = new Uri.http('news-at.zhihu.com', '/api/3/stories/latest');

  // 3、发起请求，等待请求
  var request = await httpClient.getUrl(uri);

  // 4、关闭请求，等待响应
  var response = await request.close();

  // 5、解码响应的内容
  return await response.transform(utf8.decoder).join();
}

void main(List<String> args) async {
  var result = await getDataFromZhihuAPI();
  print(result);
}
```

#### 2. Dart 中的 async 和 await

- 1、只有 async 方法才能使用 await 关键字调用方法
- 2、如果调用别的 async 方法必须使用 await 关键字
- 3、async 是让方法变成异步
- 4、await 是等待异步方法执行完成

```dart
void main(List<String> args) async {
 var result = await asyncTest();
 print('result: $result');
}

// 异步方法
asyncTest() async {
 return 'hello async';
}
```

#### 3. Dart 中的 pub 包管理系统

通过 Dart 中的 pub 包管理系统来使用第三方库，步骤：

- 1、从下面网址找到要用的库

  - https://pub.dev/packages
  - https://pub.flutter-io.cn/packages
  - https://pub.dartlang.org/flutter/

- 2、创建一个 pubspec.yaml 文件，内容如下

  ```dart
  name: projectName
  description: a new dart project.
  dependencies:
      http: ^0.12.0+2
      date_format: ^1.0.6
  ```

- 3、配置 dependencies

- 4、运行命令 pub get 获取远程库

- 5、看文档引入库使用

```dart
import 'dart:convert' as convert;
import 'package:http/http.dart' as http;
import 'package:date_format/date_format.dart';

void main(List<String> args) async {
  var response = await http.get("http://www.phonegap100.com/appapi.php?a=getPortalList&catid=20&page=1");
  if (response.statusCode == 200) {
    var jsonResponse = convert.jsonDecode(response.body);
    print(jsonResponse);
  } else {
    print("Request failed with status: ${response.statusCode}.");
  }

  print('———————————————————————————————————————————————');
  print(formatDate(DateTime(2020, 3, 11), [yyyy, '*', mm, '*', dd]));
}
```

#### 4. Dart 库的部分导入

如果只需要导入库的一部分，有两种模式：

- 1、只导入需要的部分，使用 show 关键字，如下例子所示：
  `import 'library/Animal.dart' show Animal;`
- 2、隐藏不需要的部分，使用 hide 关键字，如下例子所示： `import 'library/Animal.dart' hide Animal;`

```dart
import 'library/Animal.dart' show Animal;

void main(List<String> args) {
  Animal animal = new Animal('鸭子', 1);
  animal.printInfo();
}
```

#### 5. Dart 延迟加载（懒加载）

- Dart 延迟加载（懒加载），即在需要的时候再进行加载。
- 懒加载的最大好处是可以减少 APP 的启动时间
- 懒加载使用 deferred as 关键字来指定
- 当需要使用的时候，需要使用 loadLibrary() 方法来加载

```dart
import 'library/Animal.dart' deferred as A;
import 'package:date_format/date_format.dart' deferred as F;

void main(List<String> args) async {
  await A.loadLibrary();
  await F.loadLibrary();

  var a = new A.Animal('兔纸', 9);
  a.printInfo();

  print('——————————————————————————————————————————');

  print(F.formatDate(DateTime(2020, 02, 02), [F.yyyy, '*', F.mm, '*', F.dd]));
}
```