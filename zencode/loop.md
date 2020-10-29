# 循环

## for 循环

for 循环允许一段代码多次执行，同时能增强脚本的可读性。

让我们看看一个普通 for 循环如何使用：

```javascript
for i in 0 .. 10 { // 你可以使用 .. ，这是第一种方式
    println(i);
}

// println 函数都会被执行 10 次，同时依次输出： 0, 1, 2, 3, 4, 5, 6, 7, 8, 9。
```

其中：

> `i` 是一个变量，每次循环结束，它的数值都会 +1。从 0 开始，直到 10 结束，但不包括 10。 每次循环都会执行大括号内的语句，你也可以写多条语句。

使用 for 循环来遍历一个数组：

```javascript
var numbers as int[] = [2,4,8,16,32,64];
for i in 0 .. numbers.length {
    println(numbers[i]);
}
// 输出 2, 4, 8, 16, 32, 64

var items as IItemStack[] = [
    <minecraft:iron_ingot>,
    <minecraft:gold_ingot>,
    <minecraft:diamond>
];
for i in 0 .. items.length {
    println(items[i].displayerName);
}
// 输出 铁锭，金锭，钻石
```

## while 循环

while 循环也可以多次执行代码，当小括号内的判断表达式为 `true`时，便会执行大括号内的语句，然后再次判断表达式，`true`则继续循环，`false`则不执行循环。

```javascript
var i as int = 0;
while(i <= 10) {
    print(i);
    i = i + 1;
}
// print() 函数会执行 11 次，依次输出 i 为: 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10

var j as int = 10;
while(j >= 0) {
    print(j);
    j = j - 1;
}
// print() 函数会执行 11 次，依次输出 j 为：10, 9, 8, 7, 6, 5, 4, 3, 2, 1, 0
```

## 增强 for 循环（foreach）

增强 for 循环用来遍历数组或集合，可读性高，不需要下标，遍历每一个元素。

```javascript
// 定义一个数组并遍历
var numbers as int[] = [2,4,8,16,32,64];
for number in numbers {
    print(number);
}
```

## break 与 continue

* `break`与`continue`都可以在 for 循环和 while 循环中使用。
* 执行到`break`语句后将直接结束当前循环。

```javascript
for i in 0 .. 5 {
    if(i == 3) break; 
    print(i);
}
// i 等于 3 时，执行 break，结束循环
// 输出 0, 1, 2
```

* 执行到`continue`语句后，跳出本次循环，并进入下一次循环。

```javascript
for i in 0 .. 5 {
    if(i == 3) continue; 
    print(i);
}
// i 等于 3 时，执行 continue，跳出当前循环，并进入下一次循环
// 输出 0, 1, 2, 4, 5
```

