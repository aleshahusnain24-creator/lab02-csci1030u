# Lab 02 - Basic Python: Variables, Conditionals, and Loops

In this lab, we'll practise the building blocks from this week's lectures: storing
values in variables, doing arithmetic, making decisions with conditionals
(`if` / `elif` / `else`), and repeating work with loops. You'll write four small
functions and check them against a set of automated tests.

**Time:** this lab is meant to be finished in the 80-minute session. If you don't
finish, you may keep working during the week and submit any time up to the **first 10
minutes of next week's lab**.  After 10 minutes, though, the lab will not be accepted, 
to avoid a cascade effect.

## Getting Started

Accept the GitHub Classroom assignment invitation in Canvas (the link is in the lab
assignment on Canvas), which will clone your own copy of the repository. In the folder 
where you keep your CSCI 1030U labs:

```
git clone https://github.com/CSCI1030U/lab02-your-username
```

## Instructions

You will edit **`lab02.py`**. The four function definitions are already written for
you - **do not rename them or change their arguments**, because the tests call them by
name. Replace each `pass` with your code, and use **`return`** to send the answer back
(not `print`).

### Part 1 - `seconds_to_hms(total_seconds)`

Write the body of `seconds_to_hms`, which takes a whole number of seconds and returns
a string in the format `"H:MM:SS"` - hours, then minutes and seconds each padded to
two digits.

Hints: integer division `//` and remainder `%` are useful, here. There are 3600 seconds
in an hour and 60 in a minute. An f-string like `f"{minutes:02d}"` pads an integer to two
digits.

```python
seconds_to_hms(3661)   # returns "1:01:01"
seconds_to_hms(59)     # returns "0:00:59"
seconds_to_hms(7325)   # returns "2:02:05"
```

### Part 2 - `admission_price(age)`

Write the body of `admission_price`, which takes a person's `age` and returns a movie
ticket price (a float) according to this table:

| Age | Price |
|---|---|
| under 5 | $0.00 |
| 5 to 12 | $8.00 |
| 13 to 64 | $15.00 |
| 65 and over | $10.00 |

Use an `if` / `elif` / `else` chain. Watch the boundaries: a 5-year-old pays $8.00, a
12-year-old pays $8.00, a 13-year-old pays $15.00, and a 65-year-old pays $10.00.

```python
admission_price(3)    # returns 0.0
admission_price(10)   # returns 8.0
admission_price(30)   # returns 15.0
admission_price(70)   # returns 10.0
```

### Part 3 - `sum_multiples(limit)`

Write the body of `sum_multiples`, which returns the sum of every whole number below
`limit` that is a multiple of 3 or a multiple of 5. Use a `for` loop over `range(limit)` and
keep a running total.

For example, below 10 the multiples of 3 or 5 are 3, 5, 6, and 9, which add up to 23.

```python
sum_multiples(10)   # returns 23
sum_multiples(20)   # returns 78
sum_multiples(1)    # returns 0
```

### Part 4 - `total_of_positives(numbers)`  (stretch - optional)

Write the body of `total_of_positives`, which takes a list of numbers and returns
the sum of only the ones that are greater than zero. Loop through the list and add
up the positives.

```python
total_of_positives([1, -2, 3, -4, 5])   # returns 9
total_of_positives([-1, -2])            # returns 0
total_of_positives([10, 20])            # returns 30
```

## Verifying Correctness

Run the pre-written tests to check your work:

```
pytest
```

Read the output closely - a failing test tells you which function is wrong and shows
what it expected versus what your code returned. Fix, save, and run `pytest` again.

## Getting Help

There is a lab instructor present for the whole session. Ask them whenever you're
stuck.

*The instructor will usually help you find the problem rather than tell you how to
fix it - the goal is for you to get better at diagnosing and fixing your own bugs.*

## How to Submit

Once your tests pass (or the session is ending), commit and push:

```
git add --all
git commit -m "Lab 02 completed"
git push origin main
```

You can confirm the autograder ran correctly by opening the **Actions** tab on your repository
page in GitHub. It can take a minute or two.

## Using AI

You may use an AI assistant to **explain ideas and help you learn** - but **not to
generate code you submit** in this half of the term. Use only a **free** model, and be
ready to explain every line you wrote; the lab instructor may ask you to walk through
your code.
