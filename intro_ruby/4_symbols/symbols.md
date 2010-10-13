!SLIDE subsection

#Symbols

!SLIDE

## Duplicated objects

    @@@ ruby
    
    $ 'get'.object_id # => 2159590280
    
    $ 'get'.object_id # => 2159574160

!SLIDE

## Avoiding object duplication

    @@@ ruby
    
    $ :get.object_id # => 608508
    
    $ :get.object_id # => 608508

!SLIDE

## A symbol can return the string and integer representation of its name

    @@@ ruby
    
    $ :get.to_s # => 'get'
    
    $ :get.to_i # => 30425

!SLIDE

    @@@ ruby
    :post.class # => Symbol
    
!SLIDE

# Important fact

!SLIDE

## There is one **symbol** <br />for **every method name**<br />(:to_i, :to_s, :object_id, etc.)
