# Scripting

I attempted [Cassidoo's coding interview question of the week](https://buttondown.com/cassidoo/archive/it-takes-courage-to-grow-up-and-become-who-you).


Find the last non-repeating character in a given string. If all characters repeat, return an empty string.

Example:

nonRepeat('candy canes do taste yummy')
'u'


The solution I came up with is:

```python
def non_repeat(input: str) -> str: 

    reverse_string = input[::-1]
    already_tried = []

    for c in reverse_string:
        if c not in already_tried and input.count(c) < 2:
            print(c) 
            return c
        else:
            already_tried.append(c)
    return ""
```

I ran the problem through AI, and this is its solution:

```
def nonRepeat(s):
    # Dictionary to store the count of each character
    char_count = {}

    # First pass: count each character
    for char in s:
        char_count[char] = char_count.get(char, 0) + 1

    # Second pass (in reverse): find the last character with count == 1
    for char in reversed(s):
        if char_count[char] == 1:
            return char

    # If no non-repeating character is found
    return ''
```

ChatGPT gave me a lot of good feedback on my attempt.

First, my solution is inefficient because of the excessive invocations of count(), whereas the AI solution iterates over the string exactly once. So my solution, according to ChatGPT, is O(n) for every character in the string, or O(n²), but the correct solution is O(n).

Second, I learned about the reversed() function, which I had never heard of. It returns a reversed iterator object, which makes it handy for iterating over a string in reverse.

Finally, I learned that the get() method accepts a second parameter that defines a default value when that value has not been defined, which is very handy when calling a dictionary key where the key's existence is unknown.

I enjoy these daily coding challenges. Since making the switch from software engineer to security engineer, I don't get to code as much as I used to. Additionally, I'm still very new to Python, so this helps me learn the language.

Overall, I can usually find the second best solution to a problem. For every coding problem, there are three solutions: brute force, second best, and optimal. I can usually hack out the second best, but not quite at the optimal level.


