# Reveal.js

### HTML Presentations Made Easy

Created by [Hakim El Hattab](http://hakim.se) / [@hakim](http://twitter.com/hakim)


<h2 class="base0D">Tyler Benziger</h2>

github.com/tybenz&nbsp;&nbsp;&nbsp;//&nbsp;&nbsp;&nbsp;@tybenz&nbsp;&nbsp;&nbsp;//&nbsp;&nbsp;&nbsp;tybenz.com


```
require "gem"

string = "base16"
symbol = :base16
fixnum = 0
float  = 0.00
array  = Array.new
array  = ['chris', 85]
hash   = {"test" => "test"}
regexp = /[abc]/

# This is a comment
class Person
  
  attr_accessor :name
  
  def initialize(attributes = {})
    @name = attributes[:name]
  end
  
  def self.greet
    "hello"
  end
end

person1 = Person.new(:name => "Chris")
print Person::greet, " ", person1.name, "\n"
puts "another #{Person::greet} #{person1.name}"
```


```
{~require "gem"

string = "base16"
symbol = :base16
fixnum = 0
float  = 0.00
array  = Array.new
array  = ['chris', 85]
hash   = {"test" => "test"}
regexp = /[abc]/

# This is a comment
class Person
  
  attr_accessor :name
  
  def initialize(attributes = {})
    @name = attributes[:name]
  end
  
  ~}def self.greet
    "hello"
  end{~
end

person1 = Person.new(:name => "Chris")
print Person::greet, " ", person1.name, "\n"
puts "another #{Person::greet} #{person1.name}"~}
```
