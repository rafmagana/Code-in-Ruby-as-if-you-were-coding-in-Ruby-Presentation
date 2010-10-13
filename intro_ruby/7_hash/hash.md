!SLIDE subsection

#Hashes

!SLIDE bullets incremental

# Hashes

* key-based
* dictionaries, maps

!SLIDE
    @@@ ruby
    ages = {"john" => 27, "peter" => 30}

!SLIDE

## Idiomatic way
    
    @@@ruby
    
    ages = Hash['john', 27, 'peter', 30]
    
    # => {"john" => 27, "peter" => 30}
    
!SLIDE
    @@@ ruby
    ages['john'] # => 27

!SLIDE

## Creating empty hashes
    @@@ ruby
    
    languages = {}

!SLIDE

## Using symbols as keys instead of strings
    @@@ ruby
    
    languages[:compiled] = %w/Obj-C Smalltalk/
    
    languages[:interpreted] = %w/Perl Python Ruby/

!SLIDE
    @@@ ruby
    languages[:compiled]
    
    # =>  ["Obj-C", "Smalltalk"]

!SLIDE
    @@@ ruby
    languages[:interpreted]
    
    # => ["Perl", "Python", "Ruby"]

!SLIDE
## You can use any object as key, <br />not only strings or symbols

!SLIDE

    @@@ ruby
    
    $ foo = [1, 2, 3]

!SLIDE
    @@@ ruby

    $ foo = [1, 2, 3]
    
    $ bar = Hash[foo, 'lorem']

!SLIDE
    @@@ ruby

    $ bar[foo] # => 'lorem'

!SLIDE
    @@@ ruby
    $ bar.methods

!SLIDE
    @@@ ruby
    $ bar.methods

    ["[]", "[]=", "has_key?", "each", ...]

!SLIDE
    @@@ ruby
    $ bar.[] foo # => 'lorem'