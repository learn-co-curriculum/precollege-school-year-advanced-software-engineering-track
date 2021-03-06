# Ruby Review - Full Lecture

## SWBATs

+ Recall basic Ruby syntax
+ Assign a variable to different data types
+ Call built-in Ruby methods and define their own methods
+ Understand and use arrays and hashes to organize data
+ Use methods to iterate through and manipulate data structures
+ Create classes and use attr_accessors to access data

## Motivation

In Intro to Software Engineering, you built full MVC web applications and became masters of Ruby. Even masters need practice, though, so let's go over some of the Ruby Basics before diving into the rest of the course!

## Lesson Plan

### Data Types

+ Let's start by reviewing some of the different data types in Ruby. Who remembers some of the different types of data we can store? *Teacher - have students give their own example of each data type* 
	* Strings - `"Flatiron School is great!"`
	* Integers - `42`
	* Floats - `42.57`
	* Boolean - `true`
+ Nice. Let's do a quick quiz. I'll put some data on the board, and you tell me the type. 
	* `34` - integer
	* `"No garden of one dragon"` - string
	* `"34"` - string
	* `true` - boolean
	* `"false"` - string
	* `false` - boolean

### Methods

+ Remember that different data types have different methods that we can use on them. What are some methods we can use on strings? 
	* `.reverse`
	* `.upcase`
	* `.downcase`
+ How about on integers?
	* `.to_s`
	* `.even?`
	* `.odd?`
+ What's a method that we can use to print something to our screen?
	* `puts`
+ And get content from a user?
	* `gets`
+ What about if we want to define our own method? How can we do that?

```ruby
def say_hi
	puts "Hi!!"
end
```

+ So, let's write a program that greets asks a user what their name is and gives them a personalized greeting. So the first thing we need to do is ask their name. How do I do that?
	* `puts "What's your name?"`
+ Great. Now I want to take in their name and store it as a variable. Who can help me do that?
	* `name = gets.chomp`
	* remember the `.chomp` to chomp off the enter key
+ Now, let's say their name back to them. How can we do this?
	* One way: `puts "Hello, " + name`
	* Another way: `puts "Hello, #{name}"`

#### Conditionals

+ Our program is pretty good, but what if Beyonce tries to use it? Instead of saying "Hello, Beyonce" I want it to say, "Beyonce! I LOVE YOUR MUSIC!"
+ We can write this out with a conditional statement - can someone help me?
```ruby
if name.downcase == "Beyonce" 
	puts "Beyonce! I LOVE YOUR MUSIC!"
else
	puts "Hello, #{name}"
end
```

#### Arrays and Hashes

+ Now that we've gone over some of the different types of data we use in Ruby, let's review some ways to organize it. 
+ Who remembers some basic ways we can store data in an organized way?
	* Arrays
	* Hashes
+ Can someone help me build out an array?
	* `my_array = ["Sandwich", 2, "Hello", 23.23]`
+ How do we access elements out of the array? 
	* `my_array[index]` - remember that we start counting from zero
	* `my_array[0]` gives the first element, in this case "Sandwich"
+ What are some methods that we can call on arrays?
	* `.push` - adds an item to the array
		* you can also use the shovel `<<`
	* `.pop` - removes an item from an array
	* `.include?` returns `true` or `false` if an array includes a certain item
	* `.each` - iterates through an array and lets us manipulate each item
+ What about hashes, how are they different than arrays?
	* Arrays are like ordered lists, hashes are stored by key-value pairs
	* `my_hash = {key => value}`
	* Another example: `birthday_tracker = {"Luke" => "May", "Leia" => "May", "Han" => "December"}`
+ We can access these values by the key
	* `my_hash["Luke"]` would return `"May"`
+ What are some hash methods? 
	* `.values`
	* `.keys`
	* `.length`
	* `.include?`

##### Iterating through Arrays and Hashes

+ We mentioned the `.each` method earlier. This lets us go through an array or hash and perform an action on each item in it.
	```ruby
	my_array.each do |item| #item is a placeholder for each item in the array - you can name it whatever you want!
		#do something to or with the item here!
	end

	my_hash.each do |key, value| # here, we can iterate through the keys and values
		puts "The key is #{key} and the value is #{value}"
	end 
	```
##### Nested Structures

+ Arrays and hashes can store other arrays and hashes. This can be really useful for keeping our data organized.
```ruby
stuff_in_my_house = {"food"=>["lettuce", "cereal", "popcorn"], "furniture" =>["sofa", "bed", "chair"], "electronics" => ["TV", "Laptop", "PlayStation"]}
```
+ In this example, `stuff_in_my_house["food"]` will return an array. We can treat this like any other array. For example: 
```ruby
stuff_in_my_house["food"].each do |food|
	puts "I like to eat #{food}!"
end
```

#### Object Orientation
+ Imagine if Facebook used hashes to represent all of their users. 

```ruby
steph = {
  :name => "Steph",
  :email => "coleman@flatironschool.com",
  :password => "flatiron",
  :friends => 0
}
```

+ It would be really tricky to keep track of things like friends and interests in common. Instead, we create a User template and then create instances of the user. This is called a class. Does anyone remember how to do that?

```ruby
  class User
  end

  steph = User.new
```
+ We can store our values in instance variables and access them using `attr_accessor`. This gives us "getter" and "setter" methods for each value

```ruby
  class User
  	attr_accessor :name, :email, :password, :friends

  	def initialize(name, email, password)
  		@name = name
  		@email = email
  		@password = password
  		@friends = []
  	end
  end

  steph = User.new("Stephanie", "coleman@flatironschool.com", "flatiron")

```
+ Each new instance of a user will get a different name, email, password, and array of friends. What if we wanted a variable to keep track of the total number of users that have been created? 
+ We can use a class constant - a variable which will belong to the entire class of User. In Ruby, we specify this by using ALL_CAPS
```ruby
  class User

  	ALL_USERS = 0

  	attr_accessor :name, :email, :password, :friends

  	def initialize(name, email, password)
  		@name = name
  		@email = email
  		@password = password
  		@friends = []
  		ALL_USERS += 1
  	end
  end

  steph = User.new("Stephanie", "coleman@flatironschool.com", "flatiron")

```
+ Notice that every time we a new user is initialized, we increase our ALL_USERS counter by one. 
+ But how do we access the `ALL_USERS` variable from outside of our class? How can we ask the User class how many users have been created? 
+ For this, we need a class method. Class methods are called on the class instead of instances of the class. For example, we'd like to say `User.all` and have that return our `ALL_USERS` variable. We define class variables using Ruby's keyword `self`. 
+ In a nutshell, `self` is a placeholder meaning "the current scope". Inside of the class, it refers to the class itself. Inside of other methods, it refers to the instance of the class. 

```ruby
  class User

  	ALL_USERS = 0

  	attr_accessor :name, :email, :password, :friends

  	def initialize(name, email, password)
  		@name = name
  		@email = email
  		@password = password
  		@friends = []
  		ALL_USERS += 1
  	end

  	def self.all
  		ALL_USERS
  	end
  end

  steph = User.new("Stephanie", "coleman@flatironschool.com", "flatiron")
  current_count = User.all
  #=> 1

```

+ It would be nice if, instead of storing just the count of users, we were keeping track of the instances of users themselves. What type of Ruby object is good for holding multiple items? An array!

```ruby
  class User

  	ALL_USERS = []

  	attr_accessor :name, :email, :password, :friends

  	def initialize(name, email, password)
  		@name = name
  		@email = email
  		@password = password
  		@friends = []
  		ALL_USERS << self
  	end

  	def self.all
  		ALL_USERS
  	end
  end

  steph = User.new("Stephanie", "coleman@flatironschool.com", "flatiron")
  all_users = User.all
  #=> [#<User:0x007f8c0b2c4388 @name="Stephanie", @email="coleman@flatironschool.com", @password="flatiron", @friends=[]>] 

```

+ Remember, inside of our initialize method, self refers to the user that was just created. It's our placeholder for the current object. 


### Conclusion/So What?

+ Ruby is the foundation of everything we've done up until this point. In this course, you're going to learn how to really leverage Object Orientation to make fully featured web applications. 

### Hints and Hurdles
+ Feel free to go through the beginning very quickly if the students are picking it up
+ The concept of `self` can be confusing - let kids know that it's okay if it takes awhile for them to pick it up. You'll have more time to practice during the Fwitter lecture in the afternoon. 


