!SLIDE subsection

# Regular Expressions

!SLIDE

    @@@ ruby

    /ru(.+)/.match("ruby")

    # => #<MatchData "ruby" 1:"by">

!SLIDE

    @@@ ruby
    
    /ru(.+)/.class # => Regexp