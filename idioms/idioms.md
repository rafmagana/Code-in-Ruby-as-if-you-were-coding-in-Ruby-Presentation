!SLIDE supersection

# Other useful idioms

!SLIDE subsection

# The Splat operator

!SLIDE

    @@@ ruby
    def find(*args)
      [args, args.class]
    end
    
!SLIDE

    @@@ ruby
    find # => [[], Array]

!SLIDE

    @@@ ruby
    
    find(:all) # => [[:all], Array]
    
!SLIDE

    @@@ ruby
    find(:all, :select => "name")
    
    # => [[:all, :select => "name"], Array]
    
!SLIDE
    @@@ ruby
    colors = %w/red green/
    
!SLIDE
    @@@ ruby
    color1, color2 = *colors

!SLIDE
    @@@ ruby
    color1 # => red

!SLIDE
    @@@ ruby
    color2 # => green
    
!SLIDE
# more on the splat operator

!SLIDE small
#**http://bit.ly/raflabs_splat**

!SLIDE subsection

# Parallel assignment

!SLIDE
    @@@ ruby
    a = 1
    b = 2

!SLIDE
    @@@ ruby
    a, b = b, a
  
!SLIDE
    
    @@@ ruby
    a # => 2
    b # => 1

!SLIDE subsection
# Keyword arguments

!SLIDE
    @@@ ruby
    def full_name(data = {})
      
      data[:firstname] + data[:lastname]
      
    end

!SLIDE small

    @@@ ruby
    my_method :firstname => 'John', :lastname => 'Smith'
    
!SLIDE small

    @@@ ruby
    my_method :firstname => 'John', :lastname => 'Smith'
    
    # => John Smith