!SLIDE supersection

# Closures

!SLIDE

# Closures are anonymous functions with closed scope

!SLIDE center

## It can be **passed** around as **parameter**
## to be called **later**

!SLIDE center

## It can refer to **variables** from
## the **context** in which it was **created**

!SLIDE

# Ruby has 4 different ways of using closures

!SLIDE
# **blocks**
## { ... }
## do ... end

!SLIDE
# **Proc** class

!SLIDE
# **lambda**

!SLIDE
#**Method** class

!SLIDE subsection

# Blocks

!SLIDE

    @@@ ruby
    (1..5).each { |num| puts num }

!SLIDE

    @@@ ruby
    (1..5).each do |num|
      
      puts num
      
    end

!SLIDE

    @@@ ruby
    (1..5).each { |num| puts num }
    
    # >> 1
    # >> 2
    # >> 3
    # >> 4
    # >> 5

!SLIDE

## *Range*#**each** is a method

    @@@ ruby
    (1..5).each

!SLIDE

## We are passing a block to the *Range*#**each** method

    @@@ ruby
    
    { |num| puts num }

!SLIDE

    @@@ ruby

    { |num| puts num }

!SLIDE
    
    @@@ javascript
    function(num){ 
      print num;
    }
    
!SLIDE

    @@@ javascript
    (1..5).each function(num){ print num; }
    
!SLIDE

    @@@ ruby
    class Range

      def each

        step do |current|

          yield("~~~[#{current.to_s}]~~~")

        end

      end

    end
    
!SLIDE

    @@@ ruby
    (1..3).each { |num| puts num }

!SLIDE

    @@@ ruby
    (1..3).each { |num| puts num }
    
    # >> ~~~[1]~~~
    # >> ~~~[2]~~~
    # >> ~~~[3]~~~

!SLIDE
    @@@ ruby
    def block_caller
        yield
        yield
        yield
    end

!SLIDE
    @@@ ruby
    def block_caller
        yield
        yield
        yield
    end

    x = 5

!SLIDE
    @@@ ruby
    def block_caller
        yield
        yield
        yield
    end

    x = 5
    
    puts x.to_s
    
    block_caller { x += 1 }
    
    puts x.to_s

!SLIDE
    @@@ ruby
    def block_caller(&block)
      block.call
      block.call
      block.call
    end

!SLIDE
    @@@ ruby
    def block_caller(&block)
      block.call
      block.call
      block.call
    end

    x = 5

!SLIDE
    @@@ ruby
    def block_caller(&block)
      block.call
      block.call
      block.call
    end

    x = 5

    puts x.to_s

    block_caller { x += 1 }

    puts x.to_s
!SLIDE
    @@@ ruby
    def block_caller(&block)
      block.call
      block.call
      block.call
    end

    x = 5

    puts x.to_s # => 5

    block_caller { x += 1 }

    puts x.to_s # => 8
    
!SLIDE subsection

# Proc

!SLIDE

## A proc is like a block but it can be saved for reuse

!SLIDE
    @@@ ruby
    square = { |num| puts num ** 2 }

!SLIDE
    @@@ ruby
    square = { |num| puts num ** 2 }
    
    # => Syntax error

!SLIDE
    @@@ ruby
    square = Proc.new { |num| puts num ** 2 }
    
!SLIDE
    @@@ ruby
    square.call 4 # => 16
    
!SLIDE

# Let's use our reusable proc

!SLIDE
    @@@ ruby
    (1..3).each square


!SLIDE
    @@@ ruby
    (1..3).each square
    
    # => wrong number of arguments (1 for 0)
    
!SLIDE

# The *Range*#**each** method doesn't expects any explicit argument

!SLIDE

# But every method accepts an implicit argument

!SLIDE

# But every method accepts an implicit argument
<br />
# A block

!SLIDE

# **square** is a proc
# let's turn it into a block

!SLIDE
    @@@ ruby
    (1..3).each &square

!SLIDE
    @@@ ruby
    (1..3).each &square
    
    # >> 1
    # >> 4
    # >> 9    

!SLIDE
    @@@ ruby
    [1, 2, 3].each &squares

!SLIDE
    @@@ ruby
    [1, 2, 3].each &square

    # >> 1
    # >> 4
    # >> 9
    
!SLIDE subsection

# lambda

!SLIDE
    @@@ ruby
    square = Proc.new { |num| puts num ** 2 }

!SLIDE
    @@@ ruby
    square = proc { |num| puts num ** 2 }

!SLIDE
    @@@ ruby
    square = lambda { |num| puts num ** 2 }

!SLIDE
    @@@ ruby
    Proc.new { }.class # => Proc

!SLIDE
    @@@ ruby
    proc { }.class # => Proc

!SLIDE
    @@@ ruby
    lambda { }.class # => Proc

!SLIDE
    @@@ ruby
    Proc.class # => Class

!SLIDE subsection

# Method class

!SLIDE

    @@@ ruby
    def sum(num)
      puts num + 2
    end

!SLIDE
    @@@ ruby
    method(:sum).class # => Method

!SLIDE
    @@@ ruby
    sum_method = method(:sum)

!SLIDE
    @@@ ruby
    sum_method.call(2) # => 4
    
!SLIDE
    @@@ ruby
    [1,2,3,4].each &method(:sum)
    
!SLIDE
    @@@ ruby
    [1,2,3,4].each &method(:sum)
    
    # >> 3
    # >> 4
    # >> 5
    # >> 6