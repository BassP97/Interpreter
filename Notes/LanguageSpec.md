## Our language: pecanPy
Pecan pie is a great kind of pie! 

pecanPy has the following constructs:
- `Integer` variables (64 bit, so a pedant might say that it supports `long` variables)
- Addition (+), subtraction (-), multiplication (*), and division (/) (long division haha get it)
- `if/elif/else` statements
- `while` loops
- `print` statements
- Functions

To elaborate:

### Variables

All variables are `long`s (sorta, for now, let's assume they are for the sake of argument). Non-zero values are treated as true, while zero values are treated as false (like C). You can alter the values of variables using "standard" arithmetic operators (+,-,/,*). Importantly, `pecanPy` has two variable assignment operators:

- =
- <==

The former creates a copy of another variable, while the latter creates a second reference to said variable - ie `x = y; x = x+1;` will increment x by one, but y will retain its value. Conversely, `x <== y; x = x+1;` will increment the value referenced by x and y by 1.

For those familiar with C, `x <== y` is akin to `int* x = *y;`. Importantly, `<==` can *only* be used to generate a second reference to an existing variable, so constructs like `x <== y+1` and `x <== 1` are invalid. 
 
So the following is valid `pecanPy`:

```
let x = 1;
let y = x;
let z <== x;
let x = x+1;
let y = y+1;
let z = z+1;
print(x);
print(y);
print(z);
```

Which will output:

```
3
2
3
```

### If statements
Here's a valid `pecanPy` code snippet:

```
let x = 100;
if(x>10){
    // do some stuff! Pretend there's valid pecanPy code here
}elif(x<10 && x>20){
    // do some stuff! Pretend there's valid pecanPy code here
}else{
    // do some stuff! Pretend there's valid pecanPy code here
}
```

`if` statements, as illustrated above, can be followed by `elif` (else if) and `else`. Having an `else` before an `elif` is syntactically invalid (of course), as is having either an `else` or an `elif` without preceding initial `if` statement. 

