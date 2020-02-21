---
title: Storing Multiple Values in Lists
teaching: 20
exercises: 10
questions:
- "How can I store many values together?"
objectives:
- "Explain what a list is."
- "Create and index lists of simple values."
- "Change the values of individual elements"
- "Append values to an existing list"
- "Slice list elements"
keypoints:
- "`[value1, value2, value3, ...]` creates a list."
- "Lists can contain any Python object."
- "Lists are indexed and sliced with square brackets (e.g., list[0] and
list[2:9]), in the same way as strings."
- "Lists are mutable (i.e., their values can be changed in place)."
- "Strings are immutable (i.e., the characters in them cannot be changed)."
---

Similar to a string that can contain many characters,
a list is a container that can store many values.
Lists are built into the language.
We create a list by putting values inside square brackets
and separating the values with commas:

~~~
odds = [1, 3, 5, 7]
print('odds are:', odds)
~~~
{: .language-python}

~~~
odds are: [1, 3, 5, 7]
~~~
{: .output}

We can access elements of a list using indices -- numbered positions of elements in the list.
These positions are numbered starting at 0, so the first element has an index of 0.

~~~
print('first element:', odds[0])
print('last element:', odds[3])
print('"-1" element:', odds[-1])
~~~
{: .language-python}

~~~
first element: 1
last element: 7
"-1" element: 7
~~~
{: .output}

Yes, we can use negative numbers as indices in Python. When we do so, the index `-1` gives us the
last element in the list, `-2` the second to last, and so on.
Because of this, `odds[3]` and `odds[-1]` point to the same element here.

If we loop over a list, the loop variable is assigned to its elements one at a time:

~~~
for number in odds:
    print(number)
~~~
{: .language-python}

~~~
1
3
5
7
~~~
{: .output}

There is one important difference between lists and strings:
we can change the values in a list,
but we cannot change individual characters in a string.
For example:

~~~
names = ['Curie', 'Darwing', 'Turing']  # typo in Darwin's name
print('names is originally:', names)
names[1] = 'Darwin'  # correct the name
print('final value of names:', names)
~~~
{: .language-python}

~~~
names is originally: ['Curie', 'Darwing', 'Turing']
final value of names: ['Curie', 'Darwin', 'Turing']
~~~
{: .output}

works, but:

~~~
name = 'Darwin'
name[0] = 'd'
~~~
{: .language-python}

~~~
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-8-220df48aeb2e> in <module>()
      1 name = 'Darwin'
----> 2 name[0] = 'd'

TypeError: 'str' object does not support item assignment
~~~
{: .error}

does not.

> ## Ch-Ch-Ch-Ch-Changes
>
> Data which can be modified in place is called [mutable]({{ page.root }}/reference/#mutable),
> while data which cannot be modified is called [immutable]({{ page.root }}/reference/#immutable).
> Strings and numbers are immutable. This does not mean that variables with string or number values
> are constants, but when we want to change the value of a string or number variable, we can only
> replace the old value with a completely new value.
>
> Lists, on the other hand, are mutable: we can modify them after they have been
> created. We can change individual elements, append new elements, or reorder the whole list. For
> some operations, like sorting, we can choose whether to use a function that modifies the data
> in-place or a function that returns a modified copy and leaves the original unchanged.
>
> Be careful when modifying data in-place. If two variables refer to the same list, and you modify
> the list value, it will change for both variables!
>
> ~~~
> cookies = ['eggs', 'flour', 'sugar', 'butter']
> my_cookies = cookies        # <-- my_cookies and cookies point to the *same* list data in memory
> cookies[0] = 'brown eggs'
> print('Ingredients in my cookies:', my_cookies)
> ~~~
> {: .language-python}
>
> ~~~
> Ingredients in my cookies: ['brown eggs', 'flour', 'sugar', 'butter']
> ~~~
> {: .output}
>
> If you want variables with mutable values to be independent, you
> must make a copy of the value when you assign it.
>
> ~~~
> cookies =  ['eggs', 'flour', 'sugar', 'butter']
> my_cookies = list(cookies)        # <-- makes a *copy* of the list
> cookies[0] = 'brown eggs'
> print('Ingredients in my cookies:', my_cookies)
> ~~~
> {: .language-python}
>
> ~~~
> Ingredients in my cookies:  ['eggs', 'flour', 'sugar', 'butter']
> ~~~
> {: .output}
>
> Because of pitfalls like this, code which modifies data in place can be more difficult to
> understand. However, it is often far more efficient to modify a large data structure in place
> than to create a modified copy for every small change. You should consider both of these aspects
> when writing your code.
{: .callout}

> ## Heterogeneous Lists
> Lists in Python can contain elements of different types. Example:
> ~~~
> sample_ages = [10, 12.5, 'Unknown']
> ~~~
> {: .language-python}
{: .callout}

There are many ways to change the contents of lists besides assigning new values to
individual elements:

~~~
odds.append(11)
print('odds after adding a value:', odds)
~~~
{: .language-python}

~~~
odds after adding a value: [1, 3, 5, 7, 11]
~~~
{: .output}

While modifying in place, it is useful to remember that Python treats lists in a slightly
counter-intuitive way.

As we saw earlier, when we modified the `cookies` list item in-place, if we make a list, (attempt to) copy it and then modify this list, we can cause all sorts of trouble. This also applies to modifying the list using the above function:

~~~
odds = [1, 3, 5, 7]
primes = odds
primes.append(2)
print('primes:', primes)
print('odds:', odds)
~~~
{: .language-python}

~~~
primes: [1, 3, 5, 7, 2]
odds: [1, 3, 5, 7, 2]
~~~
{: .output}

This is because Python stores a list in memory, and then can use multiple names to refer to the
same list. If all we want to do is copy a (simple) list, we can again use the `list` function, so we do
not modify a list we did not mean to:

~~~
odds = [1, 3, 5, 7]
primes = list(odds)
primes.append(2)
print('primes:', primes)
print('odds:', odds)
~~~
{: .language-python}

~~~
primes: [1, 3, 5, 7, 2]
odds: [1, 3, 5, 7]
~~~
{: .output}

> ## Turn a String Into a List
>
> Use a for-loop to convert the string "hello" into a list of letters:
>
> ~~~
> ["h", "e", "l", "l", "o"]
> ~~~
> {: .language-python}
>
> Hint: You can create an empty list like this:
>
> ~~~
> my_list = []
> ~~~
> {: .language-python}
>
> > ## Solution
> > ~~~
> > my_list = []
> > for char in "hello":
> >     my_list.append(char)
> > print(my_list)
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

Subsets of lists and strings can be accessed by specifying ranges of values in brackets.
This is commonly referred to as "slicing" the list/string.

~~~
ingredient = 'brown eggs'
color = ingredient[0:5]
print("color:", color)

grocery = ingredient[6:10]
print("grocery:", grocery)

cookies = ['eggs', 'flour', 'sugar', 'butter', 'chocolate chips']
other = cookies[2:5]
print("other:", other)

last = cookies[-1]
print('last:', last)
~~~
{: .language-python}

~~~
color: brown
grocery: eggs
other: ['sugar', 'butter', 'chocolate chips']
last: chocolate chips
~~~
{: .output}

If you want to take a slice from the beginning of a sequence, you can omit the first index in the
range:

~~~
date = "Monday 4 January 2016"
day = date[0:6]
print("Using 0 to begin range:", day)
day = date[:6]
print("Omitting beginning index:", day)
~~~
{: .language-python}

~~~
Using 0 to begin range: Monday
Omitting beginning index: Monday
~~~
{: .output}

And similarly, you can omit the ending index in the range to take a slice to the very end of the
sequence:

~~~
months = ["jan", "feb", "mar", "apr", "may", "jun", "jul", "aug", "sep", "oct", "nov", "dec"]
sond = months[8:12]
print("With known last position:", sond)
sond = months[8:len(months)]
print("Using len() to get last entry:", sond)
sond = months[8:]
print("Omitting ending index:", sond)
~~~
{: .language-python}

~~~
With known last position: ["sep", "oct", "nov", "dec"]
Using len() to get last entry: ["sep", "oct", "nov", "dec"]
Omitting ending index: ["sep", "oct", "nov", "dec"]
~~~
{: .output}

{% include links.md %}
