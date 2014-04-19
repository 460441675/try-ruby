# 在线资源

## 在线编程环境

- [nitrous.io](https://www.nitrous.io)

## 在线学习资源

- [Try Ruby](http://tryruby.org)
- [Code School](https://www.codeschool.com)
- [Tree House](http://teamtreehouse.com) - 强烈推荐
- [《诱人的 Ruby》系列课程](http://edu.51cto.com/course/courseList/id-30.html)

# Ruby 简介

## 要点

1. Ruby 是一种动态语言
2. Ruby 的背景故事
3. Ruby 为什么火了起来
4. Ruby 社区的特点
5. Ruby 是高度面向对象的

# Ruby 语法基础知识

Ruby 的几种基本类型将在下面的讲解过程中依次引入。

## 1. 用 Ruby 操作数字（Number）

加法：
```ruby
2 + 6
```

减法：
```ruby
4 * 10
```

乘法：
```ruby
5 - 2
```

除法：
```ruby
40 / 4
```

## 2. 用 Ruby 操作字符串（String）

输出字符串：
```ruby
"Jimmy"
```

反转字符串：
```ruby
"Jimmy".reverse
```

计算字符串长度：
```ruby
"Jimmy".length
```

重复输出字符串：
```ruby
"Jimmy" * 5
```

## 3. 数据类型的相互转换

数字能被反转吗？
```ruby
40.reverse # Oppse! 这行代码会失败的，数字类型不能被反转。
40.to_s.reverse # 这样就对了，to_s 会尝试将任何一个对象转换成字符串，是英文 to string 的缩写。
```

其他几种转换方法（不全）：
```
to_s 将对象转换成字符串。
to_i 将对象转换成整形（数字）。
to_a 将对象转换成数组。
```

## 4. 数组（Array）

一个空的数组：
```ruby
[]
```

含有内容的数组：
```ruby
[12, 47, 35] # 数组中的元素是有顺序的，序号从0开始。
[12, 47, 35][1] # 取出第二个元素。
[12, 'Hello World!', 35] # 数组可以包含不同类型的元素。
```

取出数组中最大的数字：
```ruby
[12, 47, 35].max
```

## 5. 变量

上面一遍一遍的输入数组太累了，如果数组包含100个元素，难道我们还要一遍一遍的输入吗？

让我们来用变量保存他！

用一个变量来保存数组：
```ruby
ticket = [12, 47, 35] # 这里引入了变量的概念
```

尝试输出一下变量：
```ruby
ticket
```

排序数组中的内容：
```ruby
# 感叹号 '!' 在 ruby 中表示 'bang! 方法', 在不同的场合有不同的作用，在这里是改变数组本身，
# 如不加感叹号，那么 sort 方法则是返回一个新的数组，而不会改变变量所保存的数组本身。
ticket.sort!
```

## 6. 变量、字符串与数组不得不说的故事

这里旨在向大家展示字符串与数组相互转换所带来的便利性。

如何快速替换文本中的文字：
```ruby
text = "Hello World!"
test["World"] = "China" # 方括号中的内容会匹配文本中第一个与之相符的字符串。
test # 看看替换的结果

# 让我们再看看如何判断字符串中是否包含指定的内容，这里引入了布尔值的概念。
test.include? "World" # 在 ruby 中，所有返回布尔值的方法都需要在末尾加上问号，这也是更加符合自然语言的优美之处。
test.include? "China"
test.include?("China") # 这与上面的代码是一样的，ruby 可以省略掉方法签名的括号。
```

如何将一首诗的每一行反转过来：
```ruby
# 将古诗《静夜思》保存到变量 poem 中，这里的 '\n' 是换行符。
poem = "床前明月光\n疑是地上霜\n举头望明月\n低头思故乡\n"

print poem # 屏幕输出 poem，ruby 中用于屏幕输出的有 p, puts, print 三种方法，效果都不同。
poem.reverse # 看看直接反转 poem 会出现什么情况？
poem.lines.reverse # 这时候利用数组来实现我们的目标就十分方便了，lines 方法会按照每一行将文本分割成数组。
print poem.lines.reverse.join # 结合使用这些东西，就能实现我们的目标，join 方法会将数组拼接成字符串。
```
## 7. 距离（Range）

想一想，你如何利用已经学过的其他编程语言快速的生成一个包含1到10共10个数字的数组？

(需要其他语言的实现例子)

来瞧瞧 Ruby 怎么做：
```ruby
(1..10).to_a # 很帅气不是吗？
# 我在让完全不懂编程的人思考如何实现的时候，他们的思路往往是与这样的语法一致的。
# 他们觉得应该会是 '1 to 10 ...' 这样去做，这充分说明了 ruby 更加贴近自然语言的优越性。
```

## 8. 哈希（Hash）、符号（Symbol）

哈希（Hash）可以理解为一种字典集合（Dictionary），或者一种键值对的集合。

一个空的哈希：
```ruby
colors = {}
```

一个含有内容的哈希：
```ruby
colors = { red: "Red", yellow: "Yellow", blue: "Blue", green: "Green" }

colors[:blue] # 取出键为 :blue 的值

# 其中 'blue:' 和 ':blue' 这样的东西就是符号（Symbol）。
# 符号在充当键（Key）的角色时使用 'red:' 或 ':red =>' 这样的形式，后者已不推荐使用。
# 符号在充当值（Value）的角色时使用 ':red' 这样的形式。
```

哈希的键值还可以这样定义：
```ruby
# 哈希中键和值的定义可以有多种方式，
colors = { red: "Red", yellow: "Yellow", "blue" => "Blue", "green" => :green }
```

有点晦涩的符号：
```ruby
# 符号的概念和用途都比较抽象，通常用于充当哈希中的键，或者在某些场合取代字符串（符号是不可变的）。
puts "foobar".object_id
puts "foobar".object_id
puts :foobar.object_id
puts :foobar.object_id
```

## 9. 块(Block)

块相当于一段预先编写好的代码块，直等到条件适合的时候触发执行：
```ruby
# 这里使用了 each 方法用来迭代集合中的元素，花括号中的内容就叫做块（Block）
['Red', 'Yellow', 'Blue', 'Green'].each { |color| puts color.length }
```

块的另一种写法：
```ruby
# 这种 do...end 的写法一般用于包含多行代码的块
['Red', 'Yellow', 'Blue', 'Green'].each do |color|
  puts color
  puts color.length
end
```

## 10. 一个 Ruby 的杀手级示例

想一想，如何用你们所知道的其他语言快速输出10遍 "Hello World!"？

（需要其他语言的实现例子）

Ruby 是优美的：
```ruby
10.times { puts "Hello World!" }
10.times { p "Hello World!" } # 还可以更短
```
这个例子充分的说明了 Ruby 的面向对象特性，也含有很多其他前面所说到的基础知识。

## 11. 方法（Method）

一个简单的方法结构：
```ruby
def method_name
  # 逻辑代码写在这里
end # ruby 的代码块都是以 end 关键字作为结束的。
```

举例，写一个在屏幕上输出 "Hello World!" 的方法：
```ruby
def hello_world
  puts "Hello World!"
end

hello_world # 调用该方法输出文字，输出时你会发现代码返回值是 nil，这个会在后面解释到。
```

一个带输入参数的方法结构：
```ruby
def method_name(arg1, arg2, ..., argN)
  # 逻辑代码写在这里
end
```

举例，写一个能根据输入内容在屏幕上输出 "Hello <输入内容>!" 的方法：
```ruby
def hello(input_string)
  puts "Hello #{input_string}!"
end

hello("China") # 调用该方法输出文字
hello "China" # 可以省略掉括号
```

在 Ruby 中，方法都有返回值，如没有特别定义返回值，则默认返回最后一行代码的结果：
```ruby
def hello(input_string)
  puts "Hello #{input_string}!" # 需要解释下单引号和双引号的区别
  "Result" # 运行并对比一下先前的代码所输出的结果
end
```

## 12. 类（Class）
