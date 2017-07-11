# BASH

* [How do I declare a variable as an integer?](#how-do-i-declare-a-variable-as-an-integer)
* [How do I perform simple arithmetic operations?](#how-do-i-perform-simple-arithmetic-operations)
* [How do I declare a variable as an array?](#how-do-i-declare-a-variable-as-an-array)
* [How do I create an array and assign values to it at the same time?](#how-do-i-create-an-array-and-assign-values-to-it-at-the-same-time)
* [How do I create an array and assign a value to one of its indexes?](#how-do-i-create-an-array-and-assign-a-value-to-one-of-its-indexes)
* [How do I assign a value to an index of an array?](#how-do-i-assign-a-value-to-an-index-of-an-array)
* [How do I dereference a value in an array?](#how-do-i-dereference-a-value-in-an-array)
* [How do I dereference all values in an array?](#how-do-i-dereference-all-values-in-an-array)
* [How do I remove a value from an index of an array?](#how-do-i-remove-a-value-from-an-index-of-an-array)
* [How do I destroy an array?](#how-do-i-destroy-an-array)
* [How do I loop over lines from stdin?](#how-do-i-loop-over-lines-from-stdin)
* [How do I loop over lines from a file?](#how-do-i-loop-over-lines-from-a-file)
* [How do I send stdout and stderr to separate files?](#how-do-i-send-stdout-and-stderr-to-separate-files)
* [How do I send both stdout and stderr from a command to a file?](#how-do-i-send-both-stdout-and-stderr-from-a-command-to-a-file)
* [How do I create a traditional for loop?](#how-do-i-create-a-traditional-for-loop) 
* [How do I process an array with a for each?](#how-do-i-process-an-array-with-a-for-each)
* [How do I process the output of a command with a for each?](#how-do-i-process-the-output-of-a-command-with-a-for-each)
* [How do I create a function?](#how-do-i-create-a-function)
* [How do I access arguments passed to a script or function?](#how-do-i-access-arguments-passed-to-a-script-or-function)
* [How do I get the exit value of the last executed command?](#how-do-i-get-the-exit-value-of-the-last-executed-command)
* [How do I write conditional statements?](#how-do-i-write-conditional-statements)
* [How do I get a list of built-in commands?](#how-do-i-get-a-list-of-built-in-commands)
* [How do I learn more about a built-in command?](#how-do-i-learn-more-about-a-built-in-command)

## How do I declare a variable as an integer?
`declare -i VAR`

## How do I perform simple arithmetic operations?
Add two numbers and set the result to x: `(( x = 1 + 2 ))`

Reference a variable in an expression: `(( y = 1 + $x ))`

Increment a variable: `(( x++ ))`

## How do I declare a variable as an array?
`declare -a ARRAY`

## How do I create an array and assign values to it at the same time?
`ARRAY=(zero one two three)`

## How do I create an array and assign a value to one of its indexes?
`ARRAY[0]=zero`

## How do I assign a value to an index of an array?
`ARRAY[10]=ten`

## How do I dereference a value in an array?
`value=${ARRAY[0]}`

## How do I dereference all values in an array?
`values=${ARRAY[@]}`

## How do I remove a value from an index of an array?
`unset ARRAY[0]`

## How do I destroy an array?
`unset ARRAY`

## How do I loop over lines from stdin?
Use while and read.
```
while read line; do
    # do something with line
done
```

## How do I loop over lines from a file?
Use while and read and take input from a file.
<pre>
while read line; do
    # do something with line
done < <i>file</i>
</pre>

## How do I send stdout and stderr to separate files?
<tt><i>cmd</i> > <i>file.out</i> 2> <i>file.err</i></tt>

## How do I send both stdout and stderr from a command to a file?
<tt><i>cmd</i> > <i>file</i> 2>&1</tt>

or

<tt><i>cmd</i> >& <i>file</i></tt>

## How do I create a traditional for loop?
```
for ((i=0; i<$NUM; i++)); do
    # do something at i
done
```

## How do I process an array with a for each?
```
for i in ${ARRAY[@]}; do
    # do something with i
done
```

## How do I process the output of a command with a for each?
<pre>
for i in $(<i>cmd</i>); do
    # process i
done
</pre>

## How do I create a function?
```
function foo() {
    # do something
    return 0
}
```

## How do I access arguments passed to a script or function?
First argument: `$1`

Second argument: `$2`

The *n*th argument: <tt>$<i>n</i></tt>

Number of argruments passed: `$#`

All arguments: `$@`

## How do I get the exit value of the last executed command?
`$?`

## How do I write conditional statements?
In general:
<pre>
if [ <i>condition1</i> ]; then
    # if condition 1 is true then do something
elif [ <i>condition2</i> ]; then
    # else if condition 2 is true then do something
else
    # else do something
fi
</pre>

Comparing strings.
  * are equal: <tt><i>s1</i> == <i>s2</i></tt>
  * are not equal <tt><i>s1</i> != <i>s2</i></tt>
  * has nonzero length: <tt>-n <i>s1</i></tt>
  * has zero length: <tt>-z <i>s1</i></tt>

Comparing integers.
  * are equal: <tt><i>n1</i> -eq <i>n2</i></tt>
  * is greater than or equal: <tt><i>n1</i> -ge <i>n2</i></tt>
  * is greater than: <tt><i>n1</i> -gt <i>n2</i></tt>
  * is less than or equal: <tt><i>n1</i> -le <i>n2</i></tt>
  * is less than: <tt><i>n1</i> -lt <i>n2</i></tt>
  * are not equal: <tt><i>n1</i> -ne <i>n2</i></tt>

Evaluating files.
  * file exists: <tt>-e <i>file</i></tt>
  * file exists and is regular: <tt>-f <i>file</i></tt>
  * file exists and is directory: <tt>-d <i>file</i></tt>
  * file exists and is readable: <tt>-r <i>file</i></tt>
  * file exists and is writable: <tt>-w <i>file</i></tt>
  * file exists and is executable: <tt>-x <i>file</i></tt>
  * file exists and has nonzero size: <tt>-s <i>file</i></tt>

Negating Conditions: <tt>[ ! <i>condition</i> ]</tt>

ORing Conditions: <tt>[ <i>condition1</i> ] || [ <i>condition2</i> ]</tt>

ANDing Conditions: Conditions: <tt>[ <i>condition1</i> ] && [ <i>condition2</i> ]</tt>

## How do I get a list of built-in commands?
`enable -a`

## How do I learn more about a built-in command?
<tt>help <i>cmd</i></tt>
