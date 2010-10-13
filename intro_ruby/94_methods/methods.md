!SLIDE subsection

# Sharing behavior

!SLIDE

# 1. Inheritance

!SLIDE

    @@@ ruby
    class Animal [< Class]
      
      def walk
        ...
      end
  
    end

!SLIDE

    @@@ ruby
    class Dog < Animal
      
    end
    
!SLIDE

    @@@ ruby
    kaiser = Dog.new
    
    kaiser.walk
    
!SLIDE

# Animals and People can walk, let's share that behavior

!SLIDE

# 2. Mix-ins

!SLIDE

    @@@ ruby
    module Walker
      
      def walk
        'walking...'
      end
      
    end
    
!SLIDE

    @@@ ruby
    
    Walker.class # => Module
    
!SLIDE

# **Modules** are objects too

!SLIDE

## Bringing module methods as instance methods

!SLIDE

    @@@ ruby
    
    class Animal
      
      include Walker
    
    end

    class Person

      include Walker

    end

!SLIDE

    @@@ ruby
    Animal.new.walk # => 'walking...'

!SLIDE

    @@@ ruby
    Person.new.walk # => 'walking...'

!SLIDE

## Bringing module methods as class methods

!SLIDE

    @@@ ruby

    class Animal

      extend Walker

    end

    class Person

      extend Walker

    end

!SLIDE

    @@@ ruby
    Animal.walk # => 'walking...'

!SLIDE

    @@@ ruby
    Person.walk # => 'walking...'

!SLIDE subsection

# Classes can be re-opened

!SLIDE

    @@@ ruby
    "ruby".decorate # => undefined method

!SLIDE
    @@@ ruby
    class String
      
      def decorate
        "**_ #{self} _**"
      end
      
    end

!SLIDE
    
    @@@ ruby
    "ruby".decorate
    
    # => "**_ ruby _ **"

!SLIDE
    @@@ ruby
    $ 1000.decorate
    
    undefined method 'decorate'
    
!SLIDE

    @@@ ruby
    class Object

      def decorate
        "**_ #{self} _**"
      end

    end

!SLIDE

    @@@ ruby
    $ "ruby".decorate
    
    "**_ ruby _ **"
!SLIDE
    @@@ ruby
    $ 1000.decorate
    
    "**_ 1000 _ **"
!SLIDE
    @@@ ruby
    $ :post.decorate
    
    "**_ post _ **"
!SLIDE
    @@@ ruby
    $ ['ruby', ' ', 'on', ' ', 'rails'].decorate
    
    "**_ ruby on rails _**"
    
!SLIDE 

#Using mix-ins to add features to certain classes

!SLIDE
    @@@ ruby
    module Decorable
      
      def decorate
        "**_ #{self} _**"
      end

    end

!SLIDE

    @@@ ruby
    class String
      include Decorable
    end

!SLIDE

    @@@ ruby
    class Fixnum
      include Decorable
    end
    
!SLIDE

    @@@ ruby
    class ClassOnSteroids
      
      include TextUtil
      include Loggeable
      include Helpers::MyHelper
      include Formats::XMLify
      
      extend Configurable
      
    end

!SLIDE subsection

# Method names

!SLIDE

# Method names can include operators

!SLIDE

    @@@ ruby
    class WeirdNumber < Numeric
      
      def +(operand)
      end

      def -(operand)
      end
      
      def *(operand)        
      end
      
    end

!SLIDE

# Exclamation mark methods (bang methods)

## By convention they should modify the receiver

!SLIDE

    @@@ ruby
    lang = "RUBY"

!SLIDE

    @@@ ruby    
    lang.downcase # => "ruby"

!SLIDE

    @@@ ruby
    lang # => "RUBY"

!SLIDE

    @@@ ruby
    lang.downcase! # => "ruby"

!SLIDE

    @@@ ruby
    lang # => "ruby"

!SLIDE

# Question mark methods

## By convention they should return a false or true

!SLIDE center

    @@@ php
    $user->isAdmin(); # => true

!SLIDE center

    @@@ ruby
    user.admin? # => true

!SLIDE

    @@@ ruby
    array = []
    
!SLIDE

    @@@ ruby
    array.empty? # => true

!SLIDE

    @@@ ruby
    numbers = 1..5

!SLIDE

    @@@ ruby
    numbers.include? 4 # => true