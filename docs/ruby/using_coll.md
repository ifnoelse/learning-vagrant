# 常用集合的使用

## Array

### 基本用法

``` ruby
# 定义一个数组
x = [1, 2, 3, 4]
```

``` ruby
x = [1, 2, 3, 4]
puts x[2]
---
3
```

``` ruby
x = [1, 2, 3, 4]
x.delete(1)
p x
---
[2, 3, 4]
```

``` ruby
x[2] += 1
puts x[2]
---
4
```

``` ruby
x[2] = "Fish" * 3
puts x[2]
---
FishFishFish
```

``` ruby
[1, "test", 2, 3, 4].each { |element| puts element.to_s + "X" }
---
1X
testX
2X
3X
4X
```

``` ruby
x = [1, 2, 3, 4]
x.collect { |element| element * 2 }
p x
---
[1, 2, 3, 4]
```

``` ruby
a = [1, "test", 2, 3, 4]
i = 0
while (i < a.length)
  puts a[i].to_s + "X"
  i += 1
end
---
1X
testX
2X
3X
4X
```

### 栈

``` ruby
#　<< 相当于 x.push("Word")
x = []
x << "Word"
x << "Play"
x << "Fun"
puts x.pop
puts x.pop
puts x.length
---
Fun
Play
1
```

### 队列

``` ruby
a = [1, 2, 3, 4, 5]
a.unshift(0)
p a
---
[0, 1, 2, 3, 4, 5]
```

``` ruby
a = [1, 2, 3, 4, 5]
p a.shift
p a
---
1
[2, 3, 4, 5]
```

### 集合

``` ruby
x = [1, 2, 3]
y = ["a", "b", "c"]
z = x + y
p z
---
[1, 2, 3, "a", "b", "c"]
```

``` ruby
x = [1, 2, 3, 4, 5]
y = [1, 2, 3]
z = x - y
p z
---
[4, 5]
```

## Hash

``` ruby
x = { "a" => 1, "b" => 2 }
x.each { |key, value| puts "#{key} equals #{value}" }
---
a equals 1
b equals 2
```

``` ruby
x = { "a" => 1, "b" => 2, "c" => 3 }
p x.keys
---
["a", "b", "c"]
```

``` ruby
x = { "a" => 1, "b" => 2 }
x.delete("a")
p x
---
{"b"=>2}
```

``` ruby
people = {
'fred' => {
'name' => 'Fred Elliott',
'age' => 63,
'gender' => 'male',
'favorite painters' => ['Monet', 'Constable', 'Da Vinci']
},
'janet' => {
'name' => 'Janet S Porter',
'age' => 55,
'gender' => 'female'
}
}
puts people['fred']['age']
puts people['janet']['gender']
p people['janet']
---
female
{"name"=>"Janet S Porter", "age"=>55, "gender"=>"female"}
```