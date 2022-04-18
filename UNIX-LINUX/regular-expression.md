# REGULAR EXPRESSION

A expression made of

1. Atom - specifies what we are looking for and where in the text the match is made
2. Operator - to combines atoms into complex expression (optional)

## ATOMS

1. Single Character
2. Dot
3. Class
4. Anchor
5. Back Reference

### Single Character

Matches a single character

```
Ex: HELLO with L
- H with L - X
- E with L - X
- L with L - true => match
```

### DOT

Matches any single character expect a new line
Symbol: .

```
Ex: HELLO with .
- H with . true => match

Ex: \n with (.)
- new line character with . => false
```

### CLASS

Matches anyone of character set which may match any character in the input text

```
Ex: HELLO with [ABL]
- H with [ABL] - X
- E with [ABL] - X
- L with [ABL] - true => match
```

> NOTE: also can use
>
> > RANGE: [A-Z] => from A to Z  
> > EXCLUSION : [^a-z] => anything except A to Z
> >
> > > to override these values use \\  
> > > [A\-Z] => A, Z, -  
> > > [\^A] => A, ^

### ANCHORS:

One Line of Text \n

| Anchor | Means                  | Points to  |
| ------ | ---------------------- | ---------- |
| ^      | Beginning of the line  | O          |
| $      | End of the Line        | t          |
| \<     | Beginning of each word | O, L, o, T |
| />     | End of each word       | e, e, f, t |

> $ at the end of any RE means end of the line  
> ^ at the beginning of any RE means start of the line

### BACK REFERNCE

To save text in on eof nine save bufferes, when we do we can refer to the saved text using back refernce  
\1 refernce to first buffer  
\2 .... \9

## OPERATORS:

1. Sequence
2. ALternation
3. Repetition
4. Group
5. Save

### SEQUENCE

- operator is nothing
- just matches the series of atoms for RE
- this implies that there is an invisible sequence operator bw them

### ALTERNATION

Used to define one or more alternatives

1. Mr | Mrs | Ms => matches Mr, Mrs, Ms
2. Aishwarya | aish => matchs Aishwarya or aish
3. HELLO with FE|EL => tries - HE, EL, LL, LO with FE then HE, EL with EL => true

### REPETITION OPERATOR

```
\{m,n\} matches prev character m to n times
BA\{3,5\} => BAAA, BAAAA, BAAAAA

\{m\} matches prev character exactly m times
\{,m\} matches prev character to atmost m times
\{m,\} matches prev character to atleast m times
```

#### SHORTHAND OPERATORS:

| Sl.no | Symbol              | equivalent repetition operator | meaning                 |
| ----- | ------------------- | ------------------------------ | ----------------------- |
| 1     | astreik ( \* )      | \\{0,\\}                       | zero or more characters |
| 2     | plus ( + )          | \\{1, \\}                      | one or more characters  |
| 3     | question mark ( ? ) | \\{0,1\\}                      | zero or one character   |

### GROUP OPERATOR

Symbol: ( atoms )

WHen a group of characters is enclosed in paranthesis, the next operator applies to whole group, not just the prev characters

```
without group
ABC\{3\} => ABCCC

with group
A(BC)\{3\} => matches ABCBCBC
```

### SAVE

To copy a matched text string to one of the nine buffers for later refernce

```
Symbol : \(...\)

\([A-Z]\).*1 => stores the matched characters to buffer 1

```

### GREEDY ALGO

when a RE using a repeating operator is used, the repeating part treis to consume as much matching text as it can

```
String: XAYXFOONFOOAX    re: A.*FOO

X with A => X
A with A => matches
    -  now .* tries to match the rest of the string
    - A to X is matched by A.*
    - now FOO starts to match by backtracking

    FINAL MATCHED STRING
    AYXFOONFOO
```
