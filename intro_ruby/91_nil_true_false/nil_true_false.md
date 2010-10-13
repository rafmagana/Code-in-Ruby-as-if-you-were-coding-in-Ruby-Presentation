!SLIDE subsection

# nil, true, false

!SLIDE bullets incremental

* The value of **nil** is **nil**
* The value of **false** is **false**
* The value of **true** is **true**

!SLIDE bullets incremental
 
* **nil** evaluates to **false**
* **false** evaluates to **false**
* **true** and everything else evaluates to **true**

!SLIDE

# **nil** represents nullity, nothing

!SLIDE center

# **nil** is an object

!SLIDE center

    @@@ ruby
    nil.class # => NilClass
    
!SLIDE

    @@@ ruby    
    my_object = nil
    
    my_object.nil? # => true
    
!SLIDE
## Dirty way
    @@@ ruby    
    foo = nil
    
    if foo != nil && foo != false
      puts "it isn't either nil nor false"
    else
      puts "it is nil or false"
    end

    # => "it is nil or false"

!SLIDE
## Clean way
    @@@ ruby
    foo = nil

    if foo
      puts "it isn't either nil nor false"
    else
      puts "it is nil or false"
    end

    # => "it is nil or false"

!SLIDE

## Dirty way
    @@@ ruby
    
    if !foo
      puts 'it is nil'
    end
    
    # => "it is nil"
!SLIDE

## Clean way
    @@@ ruby

    unless foo
      puts 'it is nil'
    end
    
    # => "it is nil"
!SLIDE
    
## Idiomatic way

    @@@ ruby
    
    puts 'it is nil' unless foo
    
    # => "it is nil"
    
!SLIDE
    @@@ ruby
    if true
      
      'true'
      
    else
      
      'false'
      
    end

!SLIDE center

# **true** is an object

!SLIDE center

    @@@ ruby
    true.class # => TrueClass
  
!SLIDE
    @@@ ruby
    unless false
      
      'false'
      
    else
      
      'true'
      
    end

!SLIDE

# **false** is an object too

!SLIDE center

    @@@ ruby
    false.class # => FalseClass

!SLIDE small

    @@@ ruby
    
    puts "it isn't there!" unless [1,3,4,5].include? 2
    
    # => it isn't there!
    
!SLIDE 

    @@@ ruby
    
    puts "it is true" if ''
    
    # => it is true

!SLIDE

    @@@ ruby

    puts "it is true" if 0

    # => it is true
    
!SLIDE

    @@@ ruby

    puts "it is true" if []

    # => it is true
    
!SLIDE

    @@@ ruby

    puts "it is false" unless false

    # => it is false