# NLP Lab Submissions
---

# Lab 1

---

# Lab 2

Lab 2 made the use of a pretrained model

A Skipgram model was also created

So was a Continuos Bag of Words 


--- 

# Lab 3

Using regex, dates of different format and wordings are being extracted and converted to a single format in the output

```
r"(\d{1,2}) (?:st|nd|rd|th)? (?: of)? \s+ ([A-Za-z]+) ,? \s+ (\d{4})",  
```

- **r'...'**: Indicates that it is a raw string and does not treat backslashes as escape characters

- **(\d{1,2})**: Matches one or two digits representing day or month [1, 12, 31]

- **(?:st|nd|rd|th)?**: 
    - A non capturing group created by the '?:' . It groups alternatives but does not create a capturing group
    - *'st|nd|rd|th'*: Matchs the ordinal suffixes of the days (1st, 2nd, 3rd, 4th)
    - The '?' at the end of the brackets is a quantifier for 'zero or one occurence' ie it will match the date with or without the presence of the suffix

- **(?: of)?**:
    - Another non capturing group to detect presence of the word 'of' in the date
    - Another quantifier which will capture the date regardless of the presence of the word of

- **\s+**: Matches one or more whitespace characters

- **([A-Za-z]+)**:
    - Matches the presence of alphabets, for names of the month (Jan/January)
    - Parentheses create a capturing group 

- **,?**: Matches a literal comma, the '?' making it optional

- **\s+**: Matches one or more whitespace characters

- **(\d{4})**: Used to capture 4 digit numbers, to capture the year

```
r"(\d{4})-(\d{1,2})-(\d{1,2})",
```

- **(\d{4})**: Used to capture 4 digit numbers, in this case, the year

- **-**: Matches a literal hyphen

- **(\d{1,2})**: Used to capture 2 digit numbers, either the day or the month

- **-**: Matches a literal hyphen

- **(\d{1,2})**: Used to capture 2 digit numbers, either the day or the month

```
r"(\d{1,2})/(\d{1,2})/(\d{4})" 
```


--- 

# Escape Characters in Regex

### *Literal Classes*

```
\.
```
Matches a literal dot

```
\*
```
Matches a literal asterisk

```
\+
```
Matches a literal plus sign

```
\?
```
Matches a literal question mark

```
\[
```
Matches a literal opening square bracket

```
\]
```
Matches a literal closing square bracket

```
\(
```
Matches a literal opening round bracket

```
\)
```
Matches a literal closing round bracket

```
\|
```
Matches a vertical bar

---

### *Character Classes*

```
\d
```
Matches any digit character (0-9)

```
\D
```
Matches any non-digit character (^0-9)

```
\w
```
Matches word characters (alphanumeric + underscores) (a-z, A-Z, 0-9, _)

```
\W
```
Matches any non-word character (^a-z, A-Z, 0-9, _)

```
\s
```
Matches any whitespace character (spaces, tabs, newlines)

```
\S
```
Matches any non-whitespace character

---

### *Anchor Classes*

```
\b
```
Matches a word boundary ie the position between a word character and a non-word character

```
\B
```
Matches a non word boundary

---

