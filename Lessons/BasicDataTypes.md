# Basic Data Types

Ruby is a strongly object-oriented language, which means that absolutely everything in Ruby is an object, even the most basic data types. We'll start here with four Ruby's basic data types: numbers (integers and floats), strings, symbols, and Booleans (true, false and nil).

## Numbers

Ruby has all the typical math operators you would expect:

```ruby
# Addition
1 + 1 #=> 2

# Substraction
2 - 1 #=> 1

# Multiplication
2 * 2 #=> 4

# Division
10 / 5 #=> 2

# Exponent
2 ** 2 #=> 4
3 ** 4 #=> 81

# Modulus (find the remainder of division)
8 % 2 #=> (8 / 2 = 4; no remainder)
10 % 4 #=> (10 / 4 = 2; with a remainder of 2)
```

## Integers and Floats

It's important to keep in mind that when doing arithmetic with two integers in Ruby, **the result will always be an integer**.

```ruby
17 / 5 #=> 3, not 3.4
```

To obtain an accurate answer, just replace one of the integers in the expression with a float.

```ruby
17 / 5.0 #=> 3.4
```

## Converting Number Types

Ruby makes it very easy to convert floats to integers and vice versa.

```ruby
# To convert an integer to a float:
13.to_f #=> 13.0

# To convert a float to an integer:
13.0.to_i   #=> 13
13.9.to_i   #=> 13
```

As shown in the last example above, when Ruby converts a float to an integer, the decimal places are simply cut off. Ruby doesn't do any rounding in this conversion.

## Some Useful Number Methods

There are many useful methods for numbers built into Ruby.

### even?

```ruby
6.even? #=> true
7.even? #=> false
```

### odd?

```ruby
6.odd? #=> false
7.odd? #=> true
```

## Strings

### Double and Single Quotation Marks

Strings can be formed with either double _""_ or single _''_ quotation marks, also known as **strings literals**. They are pretty similar, but there are some differences. Specifically, string interpolation and the escape characters that we'll discuss soon both only work inside double quotation marks, not single quotation marks.

### Concatenation

```ruby

# With the plus operator:
"Welcome " + "to " + " Odin!" #=> "Welcome to Oding!"

# With the shovel operator:
"Welcome " << "to " << "Odin!" #=> "Welcom to Odin!"

# With the concat method
"Welcome ".concat("to ").concat("Odin!") #=> Welcome to Odin

```

### Substrings

You can access strings inside strings.

```ruby
"hello"[0]      #=> 'h'
"hello"[0..1]   #=> 'he
"hello"[0, 4]   #=> 'hell'
"hello"[-1]     #=> 'o'
```

### Escape characters

Escape characters allow you to type in representations of whitescape characters and to include quotation marks inside your string without accidentally ending it.

```ruby
\\      #=> Need a backslash in your string?
\b      #=> Backspace
\r      #=> Carriage return, for those of you that love typewritters
\n      #=> Newline. You'll likely use this one the most.
\s      #=> Space.
\t      #=> Tab.
\"      #=> Double quotation mark.
\'      #=> Single quotation mark.
```

### Interpolation

String interpolation allows you to evaluate a string that contains placeholder variables. This is very useful and common technique, so you will likely find yourself using this often. Be sure to use double quotes so that string interpolation will work.

```ruby
name = "Odin"
puts "Hello, #{name}" #=> "Hello, Odin"
puts 'Hello, #{name}' #=> "Hello, #{name}"
```

### Common Strings Methods

There are many useful strings methods that are built into Ruby.

Just remember, strings have loads of methods provided to you for free, and you can find them all in the ![ruby_docs](https://ruby-doc.org/core-3.0.3/String.html). If you're working with strings and need to do something, check in the Ruby docs first and see if there's a method that does it for you.

```ruby

"hello".capitalize      #=> "Hello"
"hello".include?("lo")  #=> true
"hello".include?("z")   #=> false
"hello".upcase          #=> "HELLO"
"Hello".downcase        #=> "hello"
"hello".empty?          #=> false
"".empty?               #=> true
"hello".length          #=> 5
"hello".reverse         #=> "olleh"
"hello world".split     #=> ["hello", "world"]
"hello".split("")       #=> ["h", "e", "l", "l", "o"]
" hello, worl ".strip   #=> "hello, world"
"he77o".sub("7", "l")   #=> "hel7o"
"he77o".gsub("7", "l")  #=> "hello"
"hello world".delete("l")   #=> "heo world"
"!".pretend("hello", "world")   #=> "hello, world!"
```

### Converting other objects to strings

Using the **to_s** method, you can convert pretty much anything to a string.

```ruby

5.to_s          #=> "5"
nil.to_s        #=> ""
:symbol.to_s    #=> "symbol"

```

## Symbols

Symbols are an interesting twist on the idea of a string.

Strings can be changed, so every time a string is used, Ruby has to store it in memory even if an existing string with the same value already exists.

Symbols no the other hand, are stored in memory only once, making them faster in certain situations.

One common application where symbols are preferred over strings are the keys in hashes.

### Create a symbol

To create a symbol, simply put a colon at the beginning of some text:

```ruby

:my_symbol

```

### Symbol bs String

To get a better idea of how symbols are stored in memory, give this a whirl in irb or a REPL.

```ruby

"string" == "string"                        #=> true
"string".object_id == "string".object_id    #=> false
:symbol.object_id == :symbol.object_id      #=> true

```

## Booleans

### True and False

### Nill

In Ruby, _nil_ represents "nothings". Everything in Ruby has a return value. When a piece of code doesn't have anything to return, it will return _nil_.
