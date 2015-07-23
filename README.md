Duck Typing
==========
Duck Typing is a concept in programming avialable to use in ruby which allows methods to to be called regardless of the object that is being passed into the method. An object only needs to have a method that responds to the method being called. 

In the code example below we have have a class called **Oven** which has the cook method. This method takes as an argument which can be any object that responds to the method **heat**

The 3 different food classed below **Pie** , **Fish** and **BakedAlaska** can all be passed into **Oven#cook** as they all have methods named heat that respond to the call to heat in Oven's cooke method. Ruby does care that different classes are being called on the same method. Also note **BakedAlaska** is being passed into **Oven#cook** as a class method rather than an instance method and Oven's cook method will call the heat method regardless of this.



```
class Oven

  def cook food
    food.heat
  end
end

class Pie

  def heat
    "gets warm"
  end
end

class Fish

  def heat
    "gets warm and smelly"
  end
end

class BakedAlaska

  def self.heat
    "gets warm on the outside, stays cold on the inside"
  end
end

oven = Oven.new
puts oven.cook(Pie.new)
puts oven.cook(Fish.new)
puts oven.cook(BakedAlaska)
```   
