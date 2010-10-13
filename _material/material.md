http://rubykoans.com/

---

Object-oriented
---------------

'string'.length 	# => 6
"stressed".reverse  #=> "desserts"
'hello'.class		# => String

6.9.class			# => Float
/^(.+)$/.class		# => Regexp

---
Syntax: Variables, constants, methods...
----------------------------------------

Variables and methods looks like. A variable can be substituted by a method.

---
Containers
----------

Array
Hash

---
Blocks and Iterators
--------------------

A function can take a block as an argument
A block is a piece of code, similar to an anonymous function, but it inherits the scope

factorial = 1

1.upto(5) do |i|
	factorial *= i
end

factorial # => 120

# block syntaxis

use do | | ... end wherever the side-effect is important
and {braces} where the return value is important.

---
Assignments
-----------

#parallel

a,b = b,a

array = [1,2,3]
a,b,c = *array

---
Conditionals
------------

# if/unless
puts 'it is empty' if array.empty?
puts 'it isn't empty unless array.empty?

#case/when
case rate
when 0..5 then 'low rate'
when 6..10 then 'high rate'
end

---
Only nil and false are false, everything else is true.
------------------------------------------------------

class Object
	def true?
		value ? true : false
	end
end

false.true? # => false

---
Ruby has a variety of loop constructs, but don’t forget the blocks!
---------------------------------------------------------------------

while/end
loop/end
for i in 0..7 / end

In Ruby loops are not used that much, we instead use blocks

---
Exception Handling
------------------

# Raising Exceptions

raise
raise 'The world is over'
raise MyCustomException, 'my custom message'

# Catching Exceptions

begin
	...
rescue 'The world is over'
	...
rescue MyCustomException
	...
ensure
	...
end

---
!SLIDE commandline incremental

# Ruby is easy to read

	$ 3.times { puts  'I cheated on you' }
	I cheated on you
	I cheated on you
	I cheated on you
	=> 3
	
	$ puts 'it is there!' if 'TextMate'.include? 'Mate'
	it is there!
	
	$ ['red', 'black'].each { |color|  puts color.capitalized }
	Red
	Black