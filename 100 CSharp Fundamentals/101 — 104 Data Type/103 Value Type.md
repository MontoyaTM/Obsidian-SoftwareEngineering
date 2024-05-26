Status: 
Tag: #ValueType 
Links: [[101 Data Type]]

---
> [!note] 
>  # Value Type

A data type is a <font style="color:#b562f9">value type</font> if it holds a data value within its <font style="color:#b562f9">own memory space</font>. It means the variables of these data types directly contain values.

``` run-csharp
int i = 100;
```

The system stores 100 in the memory space allocated for the variable `i`. The following image illustrates how 100 is stored at some hypothetical location in the memory (0x239110) for 'i':

![[Pasted image 20230508194218.png]]

## Simple Types
---
#### 1.  Integer Types: 

Integers are whole numbers that can be positive, negative, or zero. C# provides several integer types, including byte, short, int, long, sbyte, ushort, uint, and ulong. The size of an integer type determines the range of values it can hold.

#### 2.  Floating-Point Types:

Floating-point types are used to represent real numbers with fractional parts. C# provides two floating-point types, float and double. Float is a 32-bit type that can hold values with a precision of seven digits, while double is a 64-bit type that can hold values with a precision of 15-16 digits.

#### 3.  Character Types: 

Character types are used to represent single characters. C# provides two character types, char and string. Char can hold a single Unicode character, while string can hold a sequence of characters.

#### 4.  Boolean Type: 

The Boolean type is used to represent logical values, which can be either true or false.


## Enum Type
---
#### Enumerations: 

Enumerations are used to create a named set of values. An enumeration type defines a set of named constants, which can be used as symbolic names for integers.


## Struct Type
---
#### Structs: 

Structs are value types that can contain data members and methods. Structs are used to represent simple types of data.


## Nullable Types
---
#### Nullable:
As you know, a value type cannot be assigned a null value. For example, _int i = null_ will give you a compile time error.

``` run-csharp
int i = null;

```

C# 2.0 introduced nullable types that allow you to assign null to value type variables.

---
References: [[103.1 Integers]], [[103.2 Floating-Point]], [[103.3 Characters]], [[103.4 Boolean]], [[103.5 Enumerations]], [[103.6 Struct]], [[103.7 Nullable]]