# Magic-Square
Creates a magic square by randomly generating a list until the list happens to be a magic square. Done as simply as possible...

# Frequently Asked Questions
### Why?
- I wanted to remake a homework assignment I did two years ago, in one line of code

### How long did this take you?
- About an hour [but making this file is only adding to the amount of time wasted]

### Does this even work?
- Of course! TIAS!

### How does it work?
- I'm glad you asked. To be honest, I'm not sure I even know. But I split it up and added comments if that helps. 
```python
def is_magic_square(x): 
    """ There might be a more concise way to do this but it works """
    return sum([x[0],x[3],x[6]])==sum([x[1],x[4],x[7]])==sum([x[2],x[5],x[8]])==sum([x[0],x[1],x[2]])==sum([x[3],x[4],x[5]])==sum([x[6],x[7],x[8]])==sum([x[0],x[4],x[8]])==sum([x[2],x[4],x[6]])

#creates an infinite iterator that will always generate a new random list as long as you call x on it
infinite_iterator = (__import__("random").sample([1,2,3,4,5,6,7,8,9],9) for _ in __import__("itertools").repeat(1))

# the final list infinitely iterates as long as the boolean condition holds true 
# `https://stackoverflow.com/questions/2361426/get-the-first-item-from-an-iterable-that-matches-a-condition`
final_square= next(x for x in infinite_iterator if is_magic_square(x))
final_square = map(str, final_square) # just so it prints

# prints it out neatly 
# `https://stackoverflow.com/questions/35903828/how-to-print-3x3-array-in-python`
print("\n".join(map(" ".join, zip(*[iter(final_square)] * 3))))
```
### Are you okay?
:)

# Special Thanks
> to Alex Martelli and Padraic Cunningham for the two stack overflow answers which made this monstrosity much more concise
