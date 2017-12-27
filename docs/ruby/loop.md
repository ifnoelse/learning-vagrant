# 循环
``` ruby
1.upto(5) { |number| puts number }
---
1
2
3
4
5
```

``` ruby
x = 1
while x < 100
puts x
x = x * 2
end
---
1
2
4
8
16
32
64
```

``` ruby
x = 1
until x > 99
  puts x
  x = x * 2
end
---
1
2
4
8
16
32
64
```

``` ruby
10.times do |i|
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
```