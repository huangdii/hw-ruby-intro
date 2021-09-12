# When done, submit this entire file to the autograder.

# Part 1

def sum(array)
  # YOUR CODE HERE
  s = 0
  array.each {|i| s += i}
  return s
end

def max_2_sum(array)
  # YOUR CODE HERE
  s = 0
  m_array = array.max(2)
  m_array.each {|i| s += i}
  return s
end

def sum_to_n?(array, n)
  # YOUR CODE HERE
  !!array.combination(2).detect { |i, j| i + j == n }
end

# Part 2

def hello(name)
  # YOUR CODE HERE
  return "Hello, " + name
end

def starts_with_consonant?(s)
  # YOUR CODE HERE
  col = ['a', 'e', 'i', 'o', 'u']
  for i in col
      if (i == s[0]) || (i.upcase() == s[0]) || (s.length < 1) || !(s[0].match?(/[[:alpha:]]/))
          return false
      end
  end
  return true
end

def binary_multiple_of_4?(s)
  # YOUR CODE HERE
  if Integer(s, exception: false) != nil
      sb = s.to_i(2)
      if (sb % 4 == 0)
          return true
      end
  end
  return false
end

# Part 3

class BookInStock
# YOUR CODE HERE
  attr_accessor :isbn, :price
  
  def initialize(isbn, price)
    raise ArgumentError, "Improper argument" if (isbn.length < 1) || (price <= 0)
    @isbn = isbn
    @price = price
  end
  
  def price_as_string()
    return "$%0.2f" % [@price]
  end

end
