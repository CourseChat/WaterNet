---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.14.4
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

# JN from Jupytext

```{code-cell} ipython3
# Import statements
import math
import operator
#from datascience import *

```

```{code-cell} ipython3
# Import set two
import matplotlib
matplotlib.use('Agg')
#from datascience import Table
%matplotlib inline
import matplotlib.pyplot as plt
import numpy as np
plt.style.use('fivethirtyeight')
```

```{code-cell} ipython3
# import urlrequest
import urllib.request
#add urllib
import urllib
#import datascience
```

```{code-cell} ipython3
# HIDDEN
# The standard set of libraries we need
import numpy as np
import matplotlib.pyplot as plt
#%matplotlib inline

# Make plots look a little bit more fancy
#plt.style.use('fivethirtyeight')

# The standard library for data in tables
import pandas as pd

# A tiny function to read a file directly from a URL
from urllib.request import urlopen

def read_url(url):
    return urlopen(url).read().decode()
```

```{code-cell} ipython3
huck_finn_url = 'https://www.inferentialthinking.com/data/huck_finn.txt'
print(huck_finn_url)
```

```{code-cell} ipython3
#different url library
import urllib  # the lib that handles the url stuff
```

```{code-cell} ipython3
huck_finn_text = read_url(huck_finn_url)
```

```{code-cell} ipython3
# Importing necessary packages
import datetime as dt
import matplotlib.pyplot as plt
import pandas as pd
import os
import numpy as np
```

```{code-cell} ipython3
!ipython profile locate default
```

```{code-cell} ipython3
import urllib.request
```

```{code-cell} ipython3
# Read two books, fast!  Skip, old

# huck_finn_url = 'https://www.inferentialthinking.com/data/huck_finn.txt'
# huck_finn_text = read_url(huck_finn_url)

huck_finn_chapters = huck_finn_text.split('CHAPTER ')[44:]
```

```{code-cell} ipython3
# Display the chapters of Huckleberry Finn in a table. Original DS8

#Table().with_column('Chapters', huck_finn_chapters)
```

```{code-cell} ipython3
# HIDDEN fix this
# Read the text of Pride and Prejudice, split into chapters.
book_url = 'http://www.gutenberg.org/ebooks/42671.txt.utf-8'
book_text = read_url(book_url)
# Break the text into Chapters: change name from book to huck_finn
huck_finn_chapters = book_text.split('CHAPTER ')
# Drop the first "Chapter" - it's the Project Gutenberg header
huck_finn_chapters = huck_finn_chapters[0:]
```

```{code-cell} ipython3
# Show the first few words of each chapter in a table.
pd.DataFrame(huck_finn_chapters, columns=['Chapters'])
```

```{code-cell} ipython3
# Count how many times the names Jim, Tom, and Huck appear in each chapter.

#counts = Table().with_columns([
 #       'Jim', np.char.count(huck_finn_chapters, 'Jim'),
 #       'Tom', np.char.count(huck_finn_chapters, 'Tom'),
 #       'Huck', np.char.count(huck_finn_chapters, 'Huck')
  #  ])
counts = pd.DataFrame.from_dict({
        'Elizabeth': np.char.count(huck_finn_chapters, 'Elizabeth'),
        'Darcy': np.char.count(huck_finn_chapters, 'Darcy'),
        'Lydia': np.char.count(huck_finn_chapters, 'Lydia'),
        'Wickham': np.char.count(huck_finn_chapters, 'Wickham'),
        'Bingley': np.char.count(huck_finn_chapters, 'Bingley'),
        'Jane': np.char.count(huck_finn_chapters, 'Jane')},
    )

# Plot the cumulative counts:
# how many times in Chapter 1, how many times in Chapters 1 and 2, and so on.

#cum_counts = counts.cumsum().with_column('Chapter', np.arange(1, 44, 1)) Old
cum_counts = counts.cumsum()

# Add the chapter numbers
number_of_chapters = len(huck_finn_chapters)
cum_counts['Chapter'] = np.arange(number_of_chapters)

#cum_counts.plot(column_for_xticks=3)
# Do the plot
cum_counts.plot(x='Chapter')
plt.title('Cumulative Number of Times Each Name Appears');
#plt.title('Cumulative Number of Times Each Name Appears', y=1.08);
```

md cell

```{code-cell} ipython3
print(huck_finn_text)
```

```{code-cell} ipython3
little_women_url = 'https://www.inferentialthinking.com/data/little_women.txt'
little_women_text = read_url(little_women_url)
#with urllib.request.urlopen(little_women_url) as response:
#   little_women_text = response.read().decode()
#urlopen(url).read().decode()
type(little_women_text)
little_women_chapters = little_women_text.split('CHAPTER ')[1:]
```

```{code-cell} ipython3
print(little_women_text)
```

```{code-cell} ipython3
# Use another form
# Get the text for Pride and Prejudice
book_url = 'http://www.gutenberg.org/ebooks/42671.txt.utf-8'
book_text = read_url(book_url)
```

```{code-cell} ipython3
import urllib.request

req = urllib.request.Request('http://www.gutenberg.org/ebooks/42671.txt.utf-8')
with urllib.request.urlopen(req) as response:
   the_page = response.read().decode()
```

```{code-cell} ipython3
print(the_page)
```

```{code-cell} ipython3
# The chapters of Little Women, in a table

Table().with_column('Chapters', little_women_chapters)
```

```{code-cell} ipython3
# Counts of names in the chapters of Little Women

counts = Table().with_columns([
        'Amy', np.char.count(little_women_chapters, 'Amy'),
        'Beth', np.char.count(little_women_chapters, 'Beth'),
        'Jo', np.char.count(little_women_chapters, 'Jo'),
        'Meg', np.char.count(little_women_chapters, 'Meg'),
        'Laurie', np.char.count(little_women_chapters, 'Laurie'),

    ])

# Plot the cumulative counts.

cum_counts = counts.cumsum().with_column('Chapter', np.arange(1, 48, 1))
cum_counts.plot(column_for_xticks=5)
plt.title('Cumulative Number of Times Each Name Appears', y=1.08);
```

```{code-cell} ipython3
# In each chapter, count the number of all characters;
# call this the "length" of the chapter.
# Also count the number of periods.

chars_periods_huck_finn = Table().with_columns([
        'Huck Finn Chapter Length', [len(s) for s in huck_finn_chapters],
        'Number of Periods', np.char.count(huck_finn_chapters, '.')
    ])
chars_periods_little_women = Table().with_columns([
        'Little Women Chapter Length', [len(s) for s in little_women_chapters],
        'Number of Periods', np.char.count(little_women_chapters, '.')
    ])
```

```{code-cell} ipython3
chars_periods_huck_finn
```

```{code-cell} ipython3
3 * 9
```

```{code-cell} ipython3
Table()
```

```{code-cell} ipython3
Table().with_columns('Number of petals', make_array(8, 34, 5))
```

```{code-cell} ipython3
minard = Table.read_table(path_data + 'minard.csv')
minard
```

```{code-cell} ipython3
Table.read_table('https://www.inferentialthinking.com/data/sat2014.csv')
```

```{code-cell} ipython3
Table.read_table('https://www.inferentialthinking.com/data/sat2014.csv')
```

```{code-cell} ipython3
import matplotlib.pyplot as plots
```

```{code-cell} ipython3
plots.figure(figsize=(6, 6))
plots.scatter(chars_periods_huck_finn.column(1), 
              chars_periods_huck_finn.column(0), 
              color='darkblue')
plots.scatter(chars_periods_little_women.column(1), 
              chars_periods_little_women.column(0), 
              color='gold')
plots.xlabel('Number of periods in chapter')
plots.ylabel('Number of characters in chapter');
```

```{code-cell} ipython3
import numpy as np                     # Load the library

a = np.linspace(-np.pi, np.pi, 100)    # Create even grid from -π to π
b = np.cos(a)                          # Apply cosine to each element of a
c = np.sin(a)                          # Apply sin to each element of a
```

```{code-cell} ipython3
b @ c
```

```{code-cell} ipython3
from scipy.stats import norm
from scipy.integrate import quad

ϕ = norm()
value, error = quad(ϕ.pdf, -2, 2)  # Integrate using Gaussian quadrature
value
```

```{code-cell} ipython3
from sympy import Symbol

x, y = Symbol('x'), Symbol('y')  # Treat 'x' and 'y' as algebraic symbols
x + x + x + y
```

```{code-cell} ipython3
expression = (x + y)**2
expression.expand()
```

```{code-cell} ipython3
import pandas as pd
np.random.seed(1234)

data = np.random.randn(5, 2)  # 5x2 matrix of N(0, 1) random draws
dates = pd.date_range('1/1/2023', periods=5, freq="M")

df = pd.DataFrame(data, columns=('price', 'weight'), index=dates)
print(df)
```

```{code-cell} ipython3

```

```{code-cell} ipython3
maindata = pd.Series([30,40,50,10, 50], name = "main")
dates = pd.date_range('1/1/2023', periods=5, freq="Y")
df = pd.DataFrame( {"Year": dates, 'Mainbreaks/100mi/year' : maindata})
print(df)
```

```{code-cell} ipython3
# An example input vector
x = np.array(
    [ 0.4967, -0.1383,  0.6477,  1.523 , -0.2342, -0.2341,  1.5792,
      0.7674, -0.4695,  0.5426, -0.4634, -0.4657,  0.242 , -1.9133,
      -1.7249, -0.5623, -1.0128,  0.3142, -0.908 , -1.4123,  1.4656,
      -0.2258,  0.0675, -1.4247, -0.5444,  0.1109, -1.151 ,  0.3757,
      -0.6006, -0.2917, -0.6017,  1.8523])
N = len(x)

plt.plot(x)
```
