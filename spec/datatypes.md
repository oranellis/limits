# Datatypes

There are two datatypes, enums and structs. The signature of a datatype is differentiated by the name, the values (which must be common between common names), and the traits.

## Sum types

The enum type, can be one of the selected values, declared like
```
@copy @move @noreset @concurrent @heap @template(type T)
enum EnumName {
    i32 val_1,
    i32 val_2,
    CustomType val_custom_type
}
```
This begins with traits which apply to the immediately next enum or struct declared, then the enum keyword, then EnumName, then the name of the enum. Within the curly braces are comma seperated type-name pairs of which one of the values are used.

Internal values are accessed through match statements on the enum type, see structures.md -> match statements

Instances of the enum are declared as follows
```
EnumName enum_instance [val_2: -26];
```

## Product types

Product types populate all internal values are are declared as follows
```
@copy @move
struct StructName {
    i32 val_1,
    i32 val_2,
    CustomType val_custom_type
}
```
As you can see it's very similar to the enum type however initialising its members is slightly different. If left empty, the value is default initialised.

```
StructName struct_instance [
    val_1: 45,
    val_2: 65537,
    val_custom_type: CustomType[custom_type_val: 64]
];
```

## Default Values

Default values can be set in the struct or enum definition as follows which overrides the default 0 or empty initialisation.
```
@copy @move @mutable @reset @concurrent
struct StructName {
    i32 val_1 = 1,
    i32 val_2 = 2,
    CustomType val_custom_type [custom_type_val: 3]
}
```

## Templates

One special trait that can apply to structs and enums is the template trait
```
@template(type T) @template(usize N)
struct StructName {
    T special_val,
    Array<T, N> array
}
```

Using a template can be done as follows
```
StructName<i32, 6> struct_instance [
    special_val: 42,
    array: Array<i32, 6>[1,2,3,4,5,6]
];
```
