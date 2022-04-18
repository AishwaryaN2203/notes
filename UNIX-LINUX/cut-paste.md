# CUT & PASTE

### CUT = removes columns of data from a file

### PASTE = combines columns of data

### CUT EXAMPLE

```
FILENAME: cities

Chicago      IL  2783    3000    1434
Houston      TX  1630    1595    1409
LA           CA  3483    2968    1791
New York     NY  7322    7071    3311
Philadelphia PA  1588    1688    1731

(15)        (3) (5)     (5)     (5)
```

> character position

```
cut -c1-14,19-22 cities

output:

Chicago       2783
Houston       1630
LA            3483
New York      7322
Philadelphia  1588

```

> FIELD POSITION

```
cut -f1

output:

Chicago
Houston
LA
New York
Philadelphia


```

### PASTE EXAMPLE

> Need minimum two files  
> Combines files horizontally  
> <b>cat command</b> combines files vertically

```
file: fileOdd
1 11 111
3 33 313
5 55 515

file: fileEven
2 22
4 38
12 90

paste fileOdd fileEven
1 11 111 2 22
3 33 313 4 38
5 55 515 12 90
# default delimiter is space

paste -d"#" fileOdd fileEven
1 11 111#2 22
3 33 313#4 38
5 55 515#12 90
# demiliter used is #
```
