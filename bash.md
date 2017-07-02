* [How do I declare a variable as an array?](#how-do-i-declare-a-variable-as-an-array)
* [How do I create an array and assign values to it at the same time?](#how-do-i-create-an-array-and-assign-values-to-it-at-the-same-time)
* [How do I create an array and assign a value to one of its indexes?](#how-do-i-create-an-array-and-assign-a-value-to-one-of-its-indexes)
* [How do I assign a value to an index of an array?](#how-do-i-assign-a-value-to-an-index-of-an-array)
* [How do I dereference the values in an array?](#how-do-i-dereference-the-values-in-an-array)
* [How do I dereference all values in an array?](#how-do-i-dereference-all-values-in-an-array)
* [How do I remove a value from an index of an array?](#how-do-i-remove-a-value-from-an-index-of-an-array)
* [How do I destroy an array?](#how-do-i-destroy-an-array)
* [How do I loop over lines from stdin?](#how-do-i-loop-over-lines-from-stdin)
* [How do I loop over lines from a file?](#how-do-i-loop-over-lines-from-a-file)
* [How do I send both stdout and stderr from a command to a file?](#how-do-i-send-both-stdout-and-stderr-from-a-command-to-a-file)

## How do I create an array and assign values to it at the same time? ##
`ARRAY=(zero one two three)`

## How do I declare a variable as an array? ##
`declare -a ARRAY`

## How do I create an array and assign a value to one of its indexes? ##
`ARRAY[0]=zero`

## How do I assign a value to an index of an array? ##
`ARRAY[10]=ten`

## How do I dereference the values in an array? ##
`value=${ARRAY[0]}`

## How do I dereference all values in an array? ##
`values=${ARRAY[*]}`

or

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
