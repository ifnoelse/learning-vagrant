# 流程控制
``` ruby
age = 10
if age < 18
puts "You're too young to use this system"
end
---
You're too young to use this system
```

``` ruby
age = 10
if age < 18
  puts "You're too young to use this system"
else
  puts "You can use this system"
end
---
You're too young to use this system
```

``` ruby
age = 10
type = age < 18 ? "child" : "adult"
puts "You are a " + type
---
You are a child
```

``` ruby
fruit = "orange"
if fruit == "orange"
  color = "orange"
elsif fruit == "apple"
  color = "green"
elsif fruit == "banana"
  color = "yellow"
else
  color = "unknown"
end
puts fruit
---
orange
```

``` ruby
fruit = "orange"
case fruit
  when "orange"
    color = "orange"
  when "apple"
    color = "green"
  when "banana"
    color = "yellow"
  else
    color = "unknown"
end
puts fruit
---
orange
```

```ruby
fruit = "orange"
color = case fruit
          when "orange"
            "orange"
          when "apple"
            "green"
          when "banana"
            "yellow"
            Else
            "unknown"
        end
puts color
---
orange
```