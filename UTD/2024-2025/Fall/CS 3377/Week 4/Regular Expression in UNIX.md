## UNIX Filters
- `cat, ehad, tail, tee, wc`
- `cut, paste`
- `find`
- `sort, uniq`
- `tr`
## What is Regular Expression
- Describes a set of possible inpit strings
- Descend from a fundamental concept called finite automata theory
- Endemic to UNIX
- Simplest regexes are just looking for an exact math
```bash
grep "cks" input.txt # finds "cks" in the file input.txt
```
- regex can match a string in more than one place
- the `.` regex can be used to match any character
```bash
grep "o." input.txt # finds "o" + any other character in input.txt
```
## Character Classes
- `[]` can be used to match any specific set of characters.
- `[^]` can be used to negate character classes
- `[aeiou]` will match any of the listed characters
- `[kK]orn` will match korn or Korn
Ranges can also be specified in character classes:
- `[1-9]` is the same as `[123456789]`
- `[abscde]` is the same as `[a-e]`
- Multiple ranges can be combined as well
## Named Character Classes
- `[a-zA-Z]` = `[[:alpha:]]`
- `[a-zA-Z0-9]` = `[[:alpha:]]`
## Anchors
Used to match at the beginning or end of a line (or both)
## Repetition
- `*` used to define zero or more occurrences
## Match Length
A match will be the longest string that satisfies the regex.
