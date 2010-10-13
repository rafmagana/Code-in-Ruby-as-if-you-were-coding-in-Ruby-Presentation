!SLIDE subsection

# Arrays

!SLIDE bullets

# Arrays

*  index-based


!SLIDE

    @@@ ruby
    colors = %w[cyan magenta yellow black]
        
!SLIDE

    @@@ ruby
    colors = %w[cyan magenta yellow black]

    colors[0] # => "cyan"

!SLIDE

    @@@ ruby
    colors = %w[cyan magenta yellow black]

    colors.first # = > "cyan"
        
!SLIDE

    @@@ ruby
    colors = %w[cyan magenta yellow black]

    colors[1,2] # => ["magenta", "yellow"]

!SLIDE

    @@@ ruby
    colors = %w[cyan magenta yellow black]

    colors[-1] # => "black"

!SLIDE

    @@@ ruby
    colors = %w[cyan magenta yellow black]

    colors.last # => "black"

!SLIDE

    @@@ ruby    
    colors = %w[cyan magenta yellow black]

    colors[1..2] # => ["magenta", "yellow"]

!SLIDE
    @@@ ruby
    colors = %w[cyan magenta yellow black]

    colors[2..-1] # => ["yellow", "black"]

!SLIDE
    @@@ ruby
    colors = %w[cyan magenta yellow black]

    colors[2...-1] # => ["yellow"]

!SLIDE
    @@@ ruby
    $ colors.methods

!SLIDE
    @@@ ruby
    $ colors.methods
    
    ["[]", "[]=", "*", "+", "-", "<<", "each"...]

!SLIDE

## Square brackets are methods in Ruby, nothing else!

!SLIDE
    @@@ ruby
    colors = %w[cyan magenta yellow black]
    
    $ colors.[] 1..2 # => "black"

!SLIDE
    @@@ ruby
    colors = %w[cyan magenta yellow black]

    $ colors[1] = 'white'
    
    $ colors.[] = 1, 'white'
    
    ["cyan", "white", "yellow", "black"]

!SLIDE
    @@@ ruby
    cmyk = %w(cyan magenta yellow black)
    
    rgb = %w/red green black/

!SLIDE small
    @@@ ruby
    $ rgb * 2
    
    ["red", "green", "black", "red", "green", "black"]

!SLIDE smaller
    @@@ ruby
    $ rgb + cmyk
    
    ["red", "green", "black", "cyan", "magenta", "yellow", "black"]

!SLIDE small
    @@@ ruby
    known_people = %w-john peter hellen charles chris-
    
    excluded = %w!hellen charles!

!SLIDE
    @@@ ruby    
    invitees = known_people - excluded
    
    ["john", "peter", "chris"]

!SLIDE
    @@@ ruby    
    invitees << "charles"

    ["john", "peter", "chris", "charles"]

!SLIDE
    @@@ ruby
    for friend in friends
      puts friend
    end

!SLIDE

## Idiomatic way
### (Idiomatic doesn't necessarilly means shorter)
    @@@ ruby
    
    invitees.each do |friend|
      
       puts friend

    end
    
!SLIDE

## More idiomatic way
### Well, sometimes it does
    @@@ ruby

    puts *invitees