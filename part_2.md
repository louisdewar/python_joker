# Python joker part 2 (Evaluation and extension)

## Evaluation:

So you got your jokes to print out onto the screen! Yet there are some issues:
1. All the jokes are displayed at once, there is no time to let any sink in (comedic timing is important).
2. It can be difficult to know where a joke starts or ends.
3. There is no time to let people think of the answer; both the question and answer are displayed at once.
4. There is no variation in the jokes, every time you run the program the same jokes are shown to you in the same order.

### So how can we fix these issues?

1. We can put `input()` after we print each joke. This will require the user to hit enter before the code will continue so they can decide when to go onto the next one.
2. We can place a few lines once the joke has finished to help separate them out so they're easier to read. How do we do this? We need to use a special character called newline and we write it like this: `\n`. This tells the computer to add a new line whenever it is written to the terminal. Have a go by typing:
```python
print('Test\n123')
```
And you should see:
```
Test
123
```

3. This is complicated to solve. The issue is that both the question and answer to the joke is stored in the same element of the array and there is no way for the computer to separate the two. We'll talking about solving this in the next section about `Dictionaries`.
4. The solution to this is to add some randomness. We'll cover this later as an extension.

## Dictionaries

Python has a data type called a `dictionary`. When you think of a dictionary you can think of a book where you can search for a word and then find a bunch of text about it (aka the definition of the word).

Python dictionaries are very similar in the sense that there are a bunch of words with data associated with them.

For example, let's say we had a dictionary in which we defined the word `question` as `What position does a ghost play in soccer?` and then in the same `dictionary` we defined the word punchline as `Ghoulie`. This dictionary now contains two items, `question` and `punchline`. These are called `keys` and the data they relate to (the definition) are called values.

Here is some code to express the dictionary we just talked about:

```python
joke = {
    'question': 'What position does a ghost play in soccer?',
    'punchline': 'Ghoulie'
}
```

Our variable joke now contains two items, where the keys are `question` and `punchline`.
To access those fields we can use a special syntax:
```python
# Prints: What position does a ghost play in soccer?
print(joke['question'])
# Prints: Ghoulie
print(joke['punchline'])
```

**Quick tip**: the value of a dictionary doesn't actually need to be text, it could be a number or any other python object.

## Fixing our jokes array
Now we need to update our jokes array to use objects instead. Here is an example:
```python
jokes = [{
    'question': 'Why didn\'t the mummy have any friends?',
    'punchline': '(Because he was wrapped up in himself!)'
},{
    'question': 'What road has the most ghosts haunting it?',
    'punchline': '(A dead end)'
}]
```

1. Change it to make the jokes you came up with follow this format (you need to replace your old `jokes` array with this new format).
2. Fix your loop to make it have two separate print statements to print out then question and then the punchline.
3. Add pauses in between the question and punchline (use `input()` so that the use has to hit enter)

## Randomness

Now it's time to add some variation to the program.

We can use `random.randint(lower, upper)` to get a random number but first we have to import `random`. When we import modules we have to place the import statements at the top of the file:
```python
import random

# Prints a random number between 0 and 10 inclusive.
print(random.randint(0, 10))
```

How does this help us?
Let's say we have 5 jokes in our program, well instead of looping through every joke in our program we could instead pick a random number from 0 - 4 inclusive and get the joke at that index in the array and only print that one joke out. That way people can keep running our program and see different jokes whenever they run it.

```python
random_joke = jokes[random_number]
```

Why do we stop at 4?
Well arrays in python start at 0 and so 0 is our first element, 1 is our second all the way up to 4 being the fifth joke.

### Extra
Instead of manually specifying the maximum joke number - 1 each time we can use the `len` function to get our maximum joke id. This is better practise as if we add more jokes we might forget to update that number.

The len function works like this:
```python
my_array = ['a', 'b', 'c']
# Prints 3
print(len(my_array))
```

Don't forget to subtract 1 from the length when passing it as the upper number into `randint`!

## Closing notes

If you've got to here you've done a lot, but there's always more to improve. What other features would you like to improve out joke app? Can you implement them by youself? If so awesome! Otherwise ask a mentor to help out!
