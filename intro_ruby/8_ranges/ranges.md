!SLIDE subsection

#Ranges

!SLIDE bullets incremental

# Ranges

* Represents an interval
* A set of values with a **start** and an **end**

!SLIDE
    @@@ ruby
    colors = %w[cyan magenta yellow black green red]

!SLIDE small
    @@@ ruby
    colors = %w[cyan magenta yellow black green red]

    colors[1..5] 
    
    # => ["magenta", "yellow", "black", "green", "red"]

!SLIDE
    @@@ ruby    
    (1..5).to_a # => [1, 2, 3, 4, 5]

!SLIDE
    @@@ ruby    
    ('r'..'u').to_a # => ["r", "s", "t", "u"]

!SLIDE
    @@@ ruby    
    ('r'...'u').to_a # => ["r", "s", "t"]

!SLIDE
    @@@ruby
    rate = rand(100)

    puts case rate
      when 0...10   then "Lowest rate"
      when 10...50  then "Low rate"
      when 50...90  then "High rate"
      when 90...100 then "Highest rate"
    end

    # => "High rate"
    
!SLIDE
    @@@ ruby
    (0...10).class # => Range

!SLIDE
    @@@ ruby    
    (0...10).methods

!SLIDE
    @@@ ruby    
    (0...10).methods

    ["first", "last", "include?", "step", ...]

!SLIDE
    @@@ ruby    
    (0...10).include? '2' # => true

!SLIDE
    @@@ ruby    
    (0...10).step(2) # => "1"