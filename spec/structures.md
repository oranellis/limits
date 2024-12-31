# Structures

The syntax of structures in Limits. Placeholder code will be denoted with an ellipsis `...`.

## Common

Regular lines of code (end in a semicolon)
```
...;
```

Comments
```
// This is the comment
```

Docstrings, placed before a named structure
```
/// @brief This is a docstring
/// @param Parameter information
/// @return Return information
```

Return statements
```
return; // For none return type
return value; // When the structure expects to return a value
```

## Conditionals

If statement
```
if (condition) {
    ...
}
elif (condition) {
    ...
}
else {
    ...
}
```

If statement with return type
```
... = if (condition) returntype {
    ...
    return val_of_returntype;
}
elif (condition) {
    ...
    return returntype;
}
else {
    ...
    return val_of_returntype;
}
```

Match statement for sum types
```
match (value_of_sum_type) {
    (value1) {
        ...
        typeofvalue1 internal_variable = value1;
        ...
    }
    (value2: custom_name) {
        ...
        typeofvalue2 internal_variable_2 = custom_name;
        ...
    }
    (else) { // matches all other values that are not explicitly matched, type contents cannot be used.
        ...
    }
}
```

Match statement for sum types with return type
```
match (value_of_enum_type) returntype {
    (value1) {
        ...
        return returntype;
    }
    (else) {
        ...
        return returntype;
    }
}
```

## Loops

Continue, jumps to next loop iteration
```
continue;
```

Break, ends the loop
```
break;
```

Loops over an iteratable from implied start to end incrementing by one element implicitliy
```
for (iter_name, iterable_value) {
    ...
    doSomething(iter_name);
    ...
}
```

Loops over an iteratable from start to implied end incrementing by one element implicitly
```
for (iter_name, iterable_value_start, iterable_value_end) {
    ...
    doSomething(iter);
    ...
}
```

Loops over an iteratable from start to end, incrementing by a specified number of elements
```
for (iter_name, iterable_value_start, iterable_value_end, isize_increment) {
    ...
    doSomething(iter);
    ...
}
```

While loop
```
while (condition) {
    ...
}
```

## Functions

Function with no return type or args
```
fn doSomething() {
    ...
    return; // Can return early
    ...
}
```

Function with return type but no args
```
fn doSomething() returntype {
    ...
    return return_value;; // Can return early
    ...
    return other_return_value;; // Must return by the end with a value
}
```

Function with return type and args
```
fn doSomething(type1 val, i32 val2) returntype {
    ...
    i32 val3 = 1 + val2;
    ...
    return other_return_value;; // Must return by the end with a value
}
```
