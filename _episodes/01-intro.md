---
title: Python Fundamentals
teaching: 20
exercises: 10
questions:
- "What basic data types can I work with in Python?"
- "How can I create a new variable in Python?"
- "Can I change the value associated with a variable after I create it?"
objectives:
- "Assign values to variables."
keypoints:
- "Basic data types in Python include integers, strings, and floating-point numbers."
- "Use `variable = value` to assign a value to a variable in order to record it in memory."
- "Variables are created on demand whenever a value is assigned to them."
- "Use `print(something)` to display the value of `something`."
---

## Variables

Any Python interpreter can be used as a calculator:
~~~
3 + 5 * 4
~~~
{: .language-python}
~~~
23
~~~
{: .output}

This is great but not very interesting.
To do anything useful with data, we need to assign its value to a _variable_.
In Python, we can [assign]({{ page.root }}/reference/#assign) a value to a
[variable]({{ page.root }}/reference/#variable), using the equals sign `=`.
For example, to assign value `2` to a variable `flour_c`, we would execute:

~~~
flour_c = 2
~~~
{: .language-python}

From now on, whenever we use `flour_c`, Python will substitute the value we assigned to
it. In layman's terms, **a variable is a name for a value**.

In Python, variable names:

 - can include letters, digits, and underscores
 - cannot start with a digit
 - are [case sensitive]({{ page.root }}/reference/#case-sensitive).

This means that, for example:
 - `flour0` is a valid variable name, whereas `0flour` is not
 - `flour` and `Flour` are different variables

## Types of data
Python knows various types of data. Three common ones are:

* integer numbers
* floating point numbers, and
* strings.

In the example above, variable `flour_c` has an integer value of `2`.
To create a variable with a floating point value, we can execute:

~~~
flour_c = 2.0
~~~
{: .language-python}

And to create a string, we add single or double quotes around some text, for example:

~~~
flour_c_text = 'flour in cups:'
~~~
{: .language-python}

## Using Variables in Python
To display the value of a variable to the screen in Python, we can use the `print` function:

~~~
print(flour_c)
~~~
{: .language-python}

~~~
2.0
~~~
{: .output}

We can display multiple things at once using only one `print` command:

~~~
print(flour_c_text, flour_c)
~~~
{: .language-python}
~~~
flour in cups: 2.0
~~~
{: .output}


To change the value of the `flour_c` variable, we have to
**assign** `flour_c` a new value using the equals `=` sign:

~~~
flour_c = 2.5
print('flour in cups is now:', flour_c)
~~~
{: .language-python}

~~~
flour in cups is now: 2.5
~~~
{: .output}


> ## Check Your Understanding
>
> What values do the variables `mass` and `age` have after each statement in the following program?
> Test your answers by executing the commands.
>
> ~~~
> mass = 47.5
> age = 122
> mass = mass * 2.0
> age = age - 20
> print(mass, age)
> ~~~
> {: .language-python}
>
> > ## Solution
> > ~~~
> > 95.0 102
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}

{% include links.md %}
