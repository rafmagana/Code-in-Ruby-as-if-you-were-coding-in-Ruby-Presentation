Objects are behavior and state
	Behavior = methods
	State = properties
	
A class define a template to build objects of the same type

class Person(name)

	def initialize(name)
		@name = name
	end
	
	def who_am_i
		@name
	end
end

peter = Person.new 'Pedro'

peter.

for Ruby, we are sending a message to peter, the message is the method walk, we never send variables as messages to objects (encapsulation)

peter.name (wrong)

class Person(name)

	def initialize(name)
		@name = name
	end
	
	def	name
		@name
	end
end
