# Variables

Stack variables are declared as following

```limits
i32 variable_name;
```

or

```limits
i32 variable_name = 45;
```

Stack variables are immutable by default and have to be declared with their value. Mutable variables require the `mut` keyword.

```limits
mut f64 a_float = 5.87;
```

Mutability on custom types can be specified per element by including mut in 
