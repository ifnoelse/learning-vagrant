# 定义方法

## 普通方法

``` ruby
def hello
  puts "hello..."
end
hello
---
hello...
```

``` ruby
def hello(user_name)
  puts "hello...#{user_name}"
end
hello "yxy"
---
hello...yxy
```

``` ruby
def hello(user_name="邢台第一刀客")
  puts "hello...#{user_name}"
end
hello
---
hello...邢台第一刀客
```

## 使用块
``` ruby

对象.方法名(参数列表) do |块变量|
  希望循环的处理
end

或者

对象.方法名(参数列表){ |块变量| 希望循环的处理 }
```

``` ruby
[1, 2, 3, 4, 5].each do |i|
  puts i ** 2
end

或者

[1, 2, 3, 4, 5].each {|i| puts i ** 2}
---
1
4
9
16
25
```

## 定义带块的方法
### 通过yield定义带块的方法
``` ruby
def hello
  yield
end
hello {
  puts "{} 作为块"
}
hello do
  puts "do-end 作为块"
end
---
{} 作为块
do-end 作为块
```

``` ruby
def upto(n)
  i = 0
  while i <= n
    yield(i)
    i = i + 1
  end
end
upto 10 do |i|
  puts i
end
---
0
1
2
3
4
5
6
7
8
9
10
```

### 通过Proc定义带块的方法

``` ruby
def hello(&block)
  puts "the object block's class is #{block.class}"
  block.call
end
hello do
  puts "通过proc定义块"
end
---
the object block's class is Proc
通过proc定义块
```

``` ruby
def upto(n,&block)
  i = 0
  while i <= n
    block.call(i)
    i = i + 1
  end
end
upto 10 do |i|
  puts i
end
---
0
1
2
3
4
5
6
7
8
9
10
```