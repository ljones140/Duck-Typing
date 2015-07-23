Duck Typing
==========
Duck Typing is a concept in programming where within a context an object will be defined by what the context requires. A real world example may be a bed. If you want to define an object as a bed your context may be that it is flat, it is level and long enough for your body to lay on. Many objects have these properties such as a floor and a long table and in the context we require are useable as beds. Floors can be slept on if all you care about with your bed is that it is flat, level and long enough.

If you were to change your requirements for a bed however(changing the context) and perhaps you want the bed to be comfortable, have a blanket and pillow. Then the floor and table are no longer beds. 

In the example below we have used the classes Duck, Goose and Birdwatcher . We have a method is a duck which requires a duck to respond to be a duck. That is all we need in our context for the object to be a duck. Instances of the duck and birdwatcher are therefore ducks. 
```
class Duck

  def quack
    "Quack!!!!!!!!"
  end

  def walk
    "walk"
  end

  def swim
    "I am swimming"
  end
end

class Goose

  def lay_eggs
    "lay_eggs"
  end

  def walk
    "walk"
  end

  def swim
    "I am swimming"
  end
end

class Birdwatcher

  def quack
    blow_duck_caller
  end

  def blow_duck_caller
    "Quaaaaaaak!!!!!!!!!!!"
  end

  def walk
    "I am walking"
  end
end

duck = Duck.new
goose = Goose.new
twitcher = Birdwatcher.new

def is_a_duck(duck)
  return "is as duck"  if duck.respond_to?(:quack) && duck.respond_to?(:walk)
  return "not a duck"
end

puts is_a_duck(duck) #expecting this to be a duck
puts is_a_duck(goose) #expecting this not to be a duck
puts is_a_duck(twitcher) #this is also a duck as it responds to the criteria 
```   
