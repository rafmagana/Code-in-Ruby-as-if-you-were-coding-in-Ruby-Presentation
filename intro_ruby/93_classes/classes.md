!SLIDE supersection

# Class objects

!SLIDE subsection

# Class and instance methods

!SLIDE center
    @@@ ruby
    
    Animal = Class.new

!SLIDE

    @@@ ruby
    class Animal
      
      def initilize
        #executed when Animal.new is called
      end
  
      def instance_method
        'instance_method'
      end
  
      def Animal.class_instance_method
        'class_method'
      end
      
    end

!SLIDE

    @@@ ruby    
    cat = Animal.new

!SLIDE
    @@@ ruby
        
    cat.instance_method # => 'instance_method'

!SLIDE
    @@@ ruby    
    
    cat.class_instance_method # => undefined

!SLIDE
    @@@ ruby        
    Animal.class_instance_method
    
    # => 'class_instance_method'

!SLIDE
    @@@ ruby    
    
    Animal.instance_method # => undefined
    
!SLIDE subsection

# Class and instance variables

!SLIDE

#Class variables
## Available to whole inheritance tree

!SLIDE

    @@@ ruby
    class Animal
      @@class_variable = 'foo'
      
      def instance_method
        @@class_variable
      end
      
      def Animal.class_method
        @@class_variable
      end
    end

!SLIDE
  
    @@@ ruby
    
    Animal.new.instance_method # => 'foo'
    
!SLIDE

    @@@ ruby

    Animal.class_method # => 'foo'
    
!SLIDE

#Instance variables
## Available only to a specific instance of the class

!SLIDE

    @@@ ruby
    class Animal
      
      def initilize(value)
        @instance_variable = value
      end
      
      def instance_method
        @instance_variable
      end
      
      def Animal.class_method
        @instance_variable
      end
    end
        
!SLIDE
  
    @@@ ruby
    Animal.new('foo').instance_method # => 'foo'

!SLIDE

    @@@ ruby
    Animal.class_method # => nil
    
    @instance_variable not initialized
    
!SLIDE
    
#Class instance variables
## Private to the class
## Unavailable to the inheritance tree
    
!SLIDE

    @@@ ruby
    class Animal
      @class_instance_variable = 'foo'
      
      def instance_method
        @class_instance_variable
      end
      
      def Animal.class_method
        @class_instance_variable
      end
    end

!SLIDE

    @@@ ruby
    Animal.new.instance_method # => nil
    
    @class_instance_variable not initialized

!SLIDE

    @@@ ruby
    Animal.class_method # => "foo"

!SLIDE

    @@@ ruby
    class Animal
      
      @@class_variable = 'bar'
      
      @class_instance_variable = 'foo'
      
      def initialize
        @instance_variable = 'lorem'
      end

    end

!SLIDE subsection

# Accessors (setters/getters)

!SLIDE

# In Ruby we don't access variables directly

!SLIDE

    @@@ ruby
    
    class Foo
      def initialize
        @bar = 'lorem'
      end
    end

!SLIDE

    @@@ ruby
    foo = Foo.new
        
!SLIDE

    @@@ ruby
    foo.@bar
    
    # => syntax error, unexpected tIVAR

!SLIDE

    @@@ ruby
    foo.bar
    
    # => undefined method 'bar'
    
!SLIDE

#Ruby is telling us something very important here...

!SLIDE

#The thing after the dot must be **always** a method

!SLIDE

#We need to create methods to access variables

!SLIDE

    @@@ ruby
    class Animal
      
      def initialize
        @name = ''
      end

      def name
        @name
      end

      def name=(value)
        @name = value
      end
      
    end

!SLIDE

# A shorter version
    @@@ ruby
    class Animal
      attr_accessor :name, :age, :color
    end

!SLIDE

    @@@ruby
    dog = Animal.new

!SLIDE

    @@@ruby
    dog.name = 'terry'
    
!SLIDE

    @@@ruby
    dog.name # => "terry"

!SLIDE
    
##We are not accessing the **@name** variable directly <br />we do it through a method called *name*
    
!SLIDE
    
##In OOP that's called **Encapsulation**

!SLIDE
    
##Only the object itself can change its **state**

!SLIDE

    @@@ ruby
    class Animal
      
      attr_accessor :name, :color
      
      attr_writer :dob
      
      attr_reader :number_of_feet
      
    end

!SLIDE subsection

# Scope

!SLIDE

# self

!SLIDE

# A reference to the current receiver

!SLIDE

    @@@ ruby
    receiver.method

!SLIDE

# If we omit the receiver, it defaults to *self*

!SLIDE
    @@@ ruby
    def top_level_method
      'hey'
    end

!SLIDE
    @@@ ruby
    top_level_method # => "hey"

!SLIDE
    @@@ ruby
    self.top_level_method # => "hey"

!SLIDE
    @@@ ruby
    self # => main

!SLIDE
    @@@ ruby
    self.class # => Object

!SLIDE
# The **top level** is an object

!SLIDE

    @@@ ruby
    class SelfStufy
  
      puts self
        
    end
    
    # => SelfStudy

!SLIDE

    @@@ ruby
    
    class SelfStudy
      
      def instance_method
        
        puts self
        
      end
    
    end
    
    # => #<SelfStudy:0x1011b3ad0>
    
!SLIDE

    @@@ ruby

    class SelfStudy

      def self.class_method

        puts self

      end

    end
    
    # => SelfStudy