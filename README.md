Tóm tắt cú pháp Scala
=====================

Nếu bạn đã từng làm quen với Java, thì việc bắt đầu với Scala sẽ thật dễ dàng. Sự khác nhau lớn nhất về cú pháp giữa Scala và Java là việc không bắt buộc `;` khi kết thúc câu lệnh.

#Chương trình đầu tiên trong Scala

Dưới đây là đoạn code đơn giản cho phép in ra cụm từ `Hello, world!`:

```
object HelloWorld {
  def main(args: Array[String]) {
    println("Hello, world!") // in ra Hello, world!
  }
}
```

Để chạy đoạn code trên, bạn cần làm theo các bước sau:

1. Lưu file dưới dạng `*.scala` (ví dụ: `HelloWorld.scala`)
2. Chạy các lệnh

```
~ scalac HelloWorld.scala
> scala HelloWorld
Hello, world!
```

#Cú pháp cơ bản trong Scala

Những thứ cơ bản cần ghi nhớ:

1. Scala phân biệt viết thường và viết hoa (ví dụ: **Hello** và
   **hello** là hoàn khác nhau trong Scala).
2. Chữ cái đầu tiên của mỗi từ trong tên lớp phải được viết hoa (ví dụ:
   MyScalaClass).
3. Tất cả tên method phải được bắt đầu bằng chữ cái viết thường, mỗi
   từ sau từ đầu tiên phải được viết hoa (ví dụ: myMethodName()).
4. Tên file phải trùng với tên của đối tượng (ví dụ: HelloWorld là tên
   đối tượng, thì file bạn cần lưu với tên *'HelloWorld.scala'*).
5. Một chương trình Scala luôn bắt đầu với phương thức `main()`.

##Bộ định danh của Scala:
###Định danh chữ số

Chữ số trong Scala có thể được bắt đầu bằng một chữ cái hoặc dấu gạch
dưói `_`, tiếp theo sau có thể là các chữ cái, số hay dấu gạch chân `_`.
Ký tự `$` là một từ khóa riêng trong Scala, vì thế nên không được sử
dụng nó để định danh. Ví dụ:

- Khai báo đúng:

```
age, _value, __1_value
```

- Khai báo sai:

```
$salary, 123abc, -salary
```

###Định danh toán tử

Toán tử trong Scala có thể gồm 1 hoặc nhiều ký tự điều khiển. Những ký
tự này được định nghĩa trong bảng ký tự ASCII như `+, : ?, ~, #`. Ví dụ:

```
+ ++ ::: <?> :>
```

###Định danh hỗn tạp

Định danh hỗn tạp gồm có định danh chữ số nối với định danh toán tử bằng
dấu gạch dưới `_`. Ví dụ:

```
myvar_=, unary_+
```

###Định danh chữ

Định danh chữ là một chuỗi tùy ý được chứa trong `(\`...\`)`. Ví dụ:

```
`x` `<clinit>` `yield`
```

###Từ khóa trong Scala

|||||
|-|-|-|-|
|Abstract |Case    |catch   |class|
|Def      |Do      |else    |extend|
|False    |Final   |finally |for|
|forSome  |If      |implicit|import|
|Lazy     |Match   |new     |null|
|Object   |Override|package |private|
|Protected|Return  |sealed  |super|
|This     |Throw   |trait   |try|
|True     |Type    |val     |var|
|While    |With    |yield   ||
|-        |:       |=       |=>|
|<-       |<:      |<%      |>:|
|#        |@       |        ||

###Chú thích trong Scala

Scala hỗ trợ việc chú thích trong một hoặc nhiều dòng tương tự như trong
Java. Ví dụ:

```
object HelloWorld {
  /*
   * This is multi-line comment
   * This is the HelloWorld program
   */
  def main(args: Array[String]) {
    // This is single-line comment
    // Prints Hello World
    println("Hello World")
  }
}
```

###Dòng trống và khoảng trắng

Một dòng chỉ bao gồm các khoảng trắng hoặc chú thích được gọi là dòng
trống, và Scala sẽ bỏ qua nó.

###Ký tự đánh dấu dòng mới

Câu lệnh trong Scala có thể được kết thúc bằng dấu `;` hoặc xuống dòng
mới. Tuy nhiên, việc sử dụng dấu `;` là không bắt buộc trừ trường hợp
có nhiều câu lênh trong một dòng. Ví dụ:

```
val s = "hello"; println(s)
```

###Đóng gói trong Scala

Khai báo package

```
package com.liftcode.stuff
```

Import package

```
import scala.xml._
import scala.collection.mutable.HashMap
import scala.collection.immutable.{TreeMap,TreeSet}
```

#Kiểu dữ liệu trong Scala

|Loại dữ liệu|Mô tả|
|Byte|8 bit. Trong khoảng từ -128 đến 127|
|Short|16 bit. Trong khoảng -32768 đến 32767|
|Int|32 bit. Trong khoảng -2147483648 đến 2147483647|
|Long|64 bit. Trong khoảng -9223372036854775808 đến 9223372036854775807|
|Float|32 bit IEEE 754 single-precision float|
|Double|64 bit IEEE 754 double-precision float|
|Char|16 bit. Ký tự Unicode. Trong khoảng U+0000 đến U+FFFF|
|String|Một dãy các Char|
|Boolean|true/false|
|Unit|Không có giá trị|
|Null|Vô hiệu hay rỗng|
|Nothing|Kiểu phụ của mỗi kiểu dữ liệu khá, bao gồm cả không có giá trị|
|Any|Tất cả các đối tượng đều là con cháu của kiểu *Any*|
|AnyRef|Các kiểu tham chiếu đều là con cháu của kiểu *AnyRef*|

#Biến trong Scala

Có 2 cách khai báo biến trong Scala là `var` và `val`.

```
val or val VariableName : DataType [= InitialValue ]
```

Tuy nhiên, biến khai báo với `var` có giá trị thay đổi được, còn với `val` thì không.
Ví dụ:

```
var myVar : String = "Foo" // có thể thay đổi được giá trị
val myVal : String = "Foo" // Không thể thay đổi được giá trị
```

Có thể khai báo nhiều biến cùng lúc:

```
val (myVar1: Int, myVar2: String) = Pair(40, "Foo")
```

#If...else trong Scala

##Cú pháp if:

```
if(Boolean_expression) {
  // Statements will execute if the Boolean expression is true
}
```

Ví dụ:

```
object Test {
  def main(args: Array[String]) {
    var x = 10;

    if( x < 20 ) {
      println("This is if statement");
    }
  }
}
```

Kết quả:

```
scalac Test.scala
> scala Test
This is if statement
```

##Cú pháp if...else:

```
if(Boolean_expression) {
  // Statements will execute if the Boolean expression is true
} else {
  // Statements will execute if the Boolean expression is false
}
```

Ví dụ:

```
object Test {
  def main(args: Array[String]) {
    var x = 10;

    if( x > 20 ) {
      println("This is if statement");
    } else {
      println("This is else statement");
    }
  }
}
```

Kết quả:

```
scalac Test.scala
> scala Test
This is else statement
```

##Cú pháp if...else if...else:

```
if(Boolean_expression 1) {
  // Statements will execute if the Boolean expression 1 is true
} else if(Boolean_expression 2) {
  // Statements will execute if the Boolean expression 2 is true
} else if(Boolean_expression 3) {
  // Statements will execute if the Boolean expression 3 is true
} else {
  // Statements will execute if the Boolean expression is false
}
```

Ví dụ:

```
object Test {
  def main(args: Array[String]) {
    var x = 30;

    if( x == 10 ) {
      println("X is 10");
    } else if(x == 20) {
      println("X is 20");
    } else if(x == 30) {
      println("X is 30")
    } else {
      println("This is else statement");
    }
  }
}
```

Kết quả:

```
scalac Test.scala
> scala Test
X is 30
```

##Cú pháp if...else lồng nhau:

```
if(Boolean_expression 1) {
  // Statements will execute if the Boolean expression 1 is true
  if(Boolean_expression 2) {
    // Statements will execute if the Boolean expression 2 is true
  }
}
```

Ví dụ:

```
object Test {
  def main(args: Array[String]) {
    var x = 10;
    var y = 30;

    if( x == 10 ) {
      if(y == 30) {
        println("X is 10 and Y is 30");
      }
    }
  }
}
```

Kết quả:

```
scalac Test.scala
> scala Test
X is 10 and Y is 30
```

#Vòng lặp trong Scala

##Vòng lặp while

Cú pháp:

```
while(condition) {
  Statement(s);
}
```

Ví dụ:

```
object Test {
  def main(args: Array[String]) {
    var a = 10;

    while( a < 20 ) {
      println("Value of a: " + a);
      a = a + 1;
    }
  }
}
```

Kết quả:

```
> scalac Test.scala
> scala Test
Value of a: 10
Value of a: 11
Value of a: 12
Value of a: 13
Value of a: 14
Value of a: 15
Value of a: 16
Value of a: 17
Value of a: 18
Value of a: 19
```

##Vòng lặp do...while

Cú pháp:

```
do {
  statement(s);
} while( condition );
```

Ví dụ:

```
object Test {
  def main(args: Array[String]) {
    var a = 10;

    do {
      println("Value of a: " + a);
      a = a + 1
    } while( a < 20)
  }
}
```

Kết quả:

```
> scalac Test.scala
> scala Test
Value of a: 10
Value of a: 11
Value of a: 12
Value of a: 13
Value of a: 14
Value of a: 15
Value of a: 16
Value of a: 17
Value of a: 18
Value of a: 19
```

##Vòng lặp for
###Vòng lặp for trong một khoảng

Cú pháp:

```
for (var x <- Range) {
  statement(s);
}
```

Ví dụ 1: Khoảng có dạng `i to j`

```
object Test {
  def main(args: Array[String]) {
    var a = 0;

    for (a <- 1 to 10) {
      println("Value of a: " + a);
    }
  }
}
```

Kết quả:

```
> scalac Test.scala
> scala Test
Value of a: 1
Value of a: 2
Value of a: 3
Value of a: 4
Value of a: 5
Value of a: 6
Value of a: 7
Value of a: 8
Value of a: 9
Value of a: 10
```

Ví dụ 2: Khoảng có dạng `i until j`

```
object Test {
  def main(args: Array[String]) {
    var a = 0;

    for (a <- 1 until 10) {
      println("Value of a: " + a);
    }
  }
}
```

Kết quả:

```
> scalac Test.scala
> scala Test
Value of a: 1
Value of a: 2
Value of a: 3
Value of a: 4
Value of a: 5
Value of a: 6
Value of a: 7
Value of a: 8
Value of a: 9
```

Ví dụ 3: Lặp lồng nhau bằng cách dùng `;` để ngăn giữa 2 khoảng

```
object Test {
  def main(args: Array[String]) {
    var a = 0;
    var b = 0;

    for (a <- 1 to 3; b <- 1 to 3) {
      println("Value of a: " + a);
      println("Value of b: " + b);
    }
  }
}
```

Kết quả:

```
> scalac Test.scala
> scala Test
Value of a: 1
Value of b: 1
Value of a: 1
Value of b: 2
Value of a: 1
Value of b: 3
Value of a: 2
Value of b: 1
Value of a: 2
Value of b: 2
Value of a: 2
Value of b: 3
Value of a: 3
Value of b: 1
Value of a: 3
Value of b: 2
Value of a: 3
Value of b: 3
```

###Vòng lặp for với tập hợp

Cú pháp:

```
for(var x <- List) {
  statement(s);
}
```

Ví dụ:

```
object Test {
  def main(args:Array[String]) {
    var a =0;
    val numList = List(1,2,3,4,5,6);

    // for loop execution with a collection
    for(a <- numList ){
      println("Value of a: " + a );
    }
  }
}
```

Kết quả:

```
> scalac Test.scala
> scala Test
Value of a: 1
Value of a: 2
Value of a: 3
Value of a: 4
Value of a: 5
Value of a: 6
```

###Vòng lặp for với điều kiện lọc

Cú pháp:

```
for(var x <- List
    if condition1; if condition2...
   ) {
  statement(s);
}
```

Ví dụ:

```
object Test {
  def main(args:Array[String]) {
    var a =0;
    val numList = List(1,2,3,4,5,6,7,8,9,10);

    // for loop execution with a collection
    for(a <- numList
        if a != 3; if a < 8
       ){
      println("Value of a: " + a );
    }
  }
}
```

Kết quả:

```
> scalac Test.scala
> scala Test
Value of a: 1
Value of a: 2
Value of a: 4
Value of a: 5
Value of a: 6
Value of a: 7
```

#Hàm trong Scala

**Cách khai báo**

```
def functionName ([list of parameters]) : [return type]
```

Ví dụ:

```
object add {
  def addInt( a:Int, b:Int ) : Int = {
    var sum:Int = 0
    sum = a + b
    return sum
  }
}
```

**Cách gọi hàm**

```
functionName( list of parameters )
```

Ví dụ:

```
object Test {
  def main(args: Array[String]{
    println( "Return value: " + addInt(5,7) );
  }

  def addInt( a:Int, b:Int ) : Int = {
    var sum:Int = 0
    sum = a + b
    return sum
  }
}
```
