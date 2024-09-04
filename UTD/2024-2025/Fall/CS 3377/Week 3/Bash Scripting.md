```bash
country = USA

$country = USA
$echo $country # USA

$new_country = $country
$echo $new_country # USA
```
## Command Line Arguments
```bash
$1 denotes the initial argument passed
$2 denotes the second argument passed
etc

echo "Hello, $1!"
# This script takes a name as a command lline arg and prints a greeting
```
## Displaying output
```bash
echo "Hello, world!"
# Prints text to terminal

echo "This is some text." > output.txt
# Writes text to output.txt
# NOTE: the > operator overwrites a file if it already has content.

echo "This is some more text." >> output.txt
# Appends text to output.txt with the `>>` operator

ls > files.txt
# Lists the files in the current directory and writes the output to a file named files.txt with the `<`
```
## The Shebang
Bash scripts begin with the shebang. It tells the shell to execute the script via the bash shell.
```bash
#!/bin/bash

# use this to find your bash shell path
```
## Executing a bash script
```bash
chmod U+x hello.sh
# Assigns execution rights to yourself
```
## Compound comparison
`-a`: similar to `$$`
`-o`: similar to `||`

## Integer comparison
`-eq`: is equal to
```bash
if ["$a" -eq "$b"]
```
`-ne`: is not equal
```bash
if ["$a" -ne "$b"]
```
`-gt`: is greater than
```bash
if ["$a" -gt "$b"]
```
`-ge`: is greater than or equal to
```bash
if ["$a" -ge "$b"]
```
`-lt`: is less than
```bash
if ["$a" -lt "$b"]
```
`-le`: is less than or equal to
```bash
if ["$a" -le "$b"]
```




## Switch case
`case`: Begin switch case
`esac`: End switch case

#linux #unix #cs3377 #CS #utd #bash