Ruby.sublime-syntax
===================

Few minor fix for default Ruby syntax

Don't recognize 'class:' symbol in Hash as a `class` keyword.

```ruby
{ class: 1 }
# ^^^^^^
# Symbol (not class keyword)
```

Add additional scope segment to classic Symbols (also for quoted symbols)

```ruby
x = :something
#    ^^^^^^^^^
#    constant.other.symbol.ruby.18syntax
```

It makes possible to distinguish traditional notation from new one introduced in
version 1.9 in a way that is non destructive to themes which are not aware of it.

ToFix:
------

```ruby
{'quoted symbol key': 1}
#                   ^
#                   this is recognized as a conditional operator
#^^^^^^^^^^^^^^^^^^^
#this is recognized as a string
```

```ruby
match?(xyz)
#    ^^
#    this is recognized as a numeric constant
```
