---
title       : Introduction to Python for Data Analysis
description : This chapter will get you started with Python for Data Analysis. We will cover the basics of the language you will need and an overview of the Python ecosystem.
attachments :
  slides_link : https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf


--- type:MultipleChoiceExercise lang:python xp:50 skills:1 key:9a8fd577a9
## Why learn Python for data analysis?

Python has gathered a lot of interest recently as a choice of language for data analysis. Here are some reasons which go in favour of learning Python:
* Open Source – free to install
* Awesome online community
* Easy to learn
* Can become a common language for data science and production of web based analytics products

Which of the following is not a reason to learn Python for Data Analysis?


*** =instructions
- Python is easy to learn
- Python is interpreted language, hence the computation times can be high compared to compiler based languages in some cases.
- Python has good libraries for data science
- It is production ready language (from web & softare perspective)

*** =hint
Have a look at the text. Do you see your answer?

*** =pre_exercise_code
```{python}


*** =sct
```{python}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# pythonwhat Python package

msg_bad = "That is not correct!"
msg_success = "Exactly! Since Python is an interpretted language, the computation times can be on the higher side."

# Use test_mc() to grade multiple choice exercises. 
# Pass the correct option (Action, option 2 in the instructions) to correct.
# Pass the feedback messages, both positive and negative, to feedback_msgs in the appropriate order.
test_mc(1, [msg_bad, msg_bad, msg_bad, msg_success]) 
```


--- type:NormalExercise lang:python xp:100 skills:1 key:af2f6f90f3
## Plot the movies yourself

Do you remember the plot of the last exercise? Let's make an even cooler plot!

A dataset of movies, `movies`, is available in the workspace.

*** =instructions
- The first function, `np.unique()`, uses the `unique()` function of the `numpy` package to get integer values for the movie genres. You don't have to change this code, just have a look!
- Import `pyplot` in the `matplotlib` package. Set an alias for this import: `plt`.
- Use `plt.scatter()` to plot `movies.runtime` onto the x-axis, `movies.rating` onto the y-axis and use `ints` for the color of the dots. You should use the first and second positional argument, and the `c` keyword.
- Show the plot using `plt.show()`.

*** =hint
- You don't have to program anything for the first instruction, just take a look at the first line of code.
- Use `import ___ as ___` to import `matplotlib.pyplot` as `plt`.
- Use `plt.scatter(___, ___, c = ___)` for the third instruction.
- You'll always have to type in `plt.show()` to show the plot you created.

*** =pre_exercise_code
```{python}
# The pre exercise code runs code to initialize the user's workspace. You can use it for several things:

# 1. Preload a dataset. The code below will read the csv that is stored at the URL's location.
# The movies variable will be available in the user's console.
import pandas as pd
movies = pd.read_csv("http://s3.amazonaws.com/assets.datacamp.com/course/introduction_to_r/movies.csv")

# 2. Preload a package
import numpy as np
```

*** =sample_code
```{python}
# Get integer values for genres
_, ints = np.unique(movies.genre, return_inverse = True)

# Import matplotlib.pyplot


# Make a scatter plot: runtime on  x-axis, rating on y-axis and set c to ints


# Show the plot

```

*** =solution
```{python}
# Get integer values for genres
_, ints = np.unique(movies.genre, return_inverse = True)

# Import matplotlib.pyplot
import matplotlib.pyplot as plt

# Make a scatter plot: runtime on  x-axis, rating on y-axis and set c to ints
plt.scatter(movies.runtime, movies.rating, c=ints)

# Show the plot
plt.show()
```

*** =sct
```{python}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# pythonwhat Python package. Documentation can also be found at github.com/datacamp/pythonwhat/wiki

# Check if the student changed the np.unique() call
# If it's not called, we know the student removed the call.
# If it's called incorrectly, we know the student changed the call.
test_function("numpy.unique",
              not_called_msg = "Don't remove the call of `np.unique` to define `ints`.",
              incorrect_msg = "Don't change the call of `np.unique` to define `ints`.")
# Check if the student removed the ints object
test_object("ints",
            undefined_msg = "Don't remove the definition of the predefined `ints` object.",
            incorrect_msg = "Don't change the definition of the predefined `ints` object.")

# Check if the student imported matplotlib.pyplot like the solution
# Let automatic feedback message generation handle the feedback messages
test_import("matplotlib.pyplot", same_as = True)

# Check whether the student used the scatter() function correctly
# If it's used, but incorrectly, tell them to check the instructions again
test_function("matplotlib.pyplot.scatter",
              incorrect_msg = "You didn't use `plt.scatter()` correctly, have another look at the instructions.")

# Check if the student called the show() function
# Let automatic feedback message generation handle all feedback messages
test_function("matplotlib.pyplot.show")

success_msg("Great work!")
```