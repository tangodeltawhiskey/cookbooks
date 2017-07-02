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
* [How do I send both stdout and stderr from a command to a file?](#how-do-i-send-both-stdout-and-stderr-from-a-command-to-a-file)
* [How do I create a traditional for loop with?](#how-do-i-create-a-traditional-for-loop-with) 
* [How do I process an array with a for each?](#how-do-i-process-an-array-with-a-for-each)
* [How do I create a function?](#how-do-i-create-a-function)
* [How do I access arguments passed to a script or function?](#how-do-i-access-arguments-passed-to-a-script-or-function)
* [How do I access the exit value of last execute command?](#how-do-i-access-the-exit-value-of-last-execute-command)

## How do I declare a variable as an integer? ##
`declare -i VAR`

## How do I perform simple arithmetic operations? ##
Add two numbers and set the result to x: `(( x = 1 + 2 ))`

Reference a variable in an expression: `(( y = 1 + $x ))`

Increment a variable: `(( x++ ))`

## How do I declare a variable as an array? ##
`declare -a ARRAY`

## How do I create an array and assign values to it at the same time? ##
`ARRAY=(zero one two three)`

## How do I create an array and assign a value to one of its indexes? ##
`ARRAY[0]=zero`

## How do I assign a value to an index of an array? ##
`ARRAY[10]=ten`

## How do I dereference a value in an array? ##
`value=${ARRAY[0]}`

## How do I dereference all values in an array? ##
`values=${ARRAY[@]}`

## How do I remove a value from an index of an array? ##
`unset ARRAY[0]`

## How do I destroy an array? ##
`unset ARRAY`

## How do I loop over lines from stdin? ##
Use while and read.
```
while read line; do
    # do something with line
done
```

## How do I loop over lines from a file? ##
Use while and read and take input from a file.
```
while read line; do
    # do something with line
done < file
```

## How do I send both stdout and stderr from a command to a file? ##
<pre>
<i>cmd</i> > </>file</i> 2>&1
</pre>

## How do I create a traditional for loop with?
```
for ((i=0; i<$NUM; i++)); do
    # do something at i
done
```

## How do I process an array with a for each?
```
for i in ${ARRAY[@]; do
    # do something with i
done
```

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

## How do I access the exit value of last execute command?
`$?`

