Status: 
Tag: #ReferenceType 
Links: [[101 Data Type]]

---

> [!note] 
>  # Reference Type

Unlike value types, a reference type doesn't store its value directly. Instead, it stores the address where the value is being stored. In other words, a reference type contains a pointer to another memory location that holds the data.

For example, consider the following string variable:

``` run-csharp
string s = "Hello World!!";

```

![[Pasted image 20230508222630.png]]

As you can see in the above image, the system selects a random location in memory <font style="color:#b562f9">(0x803200)</font> for the variable <font style="color:#b562f9">s</font>. The value of a variable <font style="color:#b562f9">s</font> is <font style="color:#b562f9">0x600000</font>, which is the memory address of the actual data value. Thus, reference type stores the address of the location where the actual value is stored instead of the value itself.

#### 1.  Arrays: 
Arrays are used to store a collection of values of the same data type. In C#, you can create arrays of any data type.

#### 2. String:

In C#, a string is a sequence of characters that represents text. In other words, a string is a data type that stores <font style="color:#b562f9">textual data</font>. Strings are reference types in C#, which means that they are stored on the heap and accessed through a reference.

#### 3. String Builder

To avoid string replacing, appending, removing or inserting new strings in the initial string C# introduce <font style="color:#b562f9">StringBuilder</font> concept. StringBuilder is a <font style="color:#b562f9">dynamic object</font>. It doesn’t create a new object in the memory but <font style="color:#81fd83">dynamically expands</font> the needed memory to accommodate the modified or new string.

#### 4. Class:

A class is a user-defined <font style="color:#b562f9">blueprint</font> or prototype from which <font style="color:#81fd83">objects</font> are created. Basically, a <font style="color:#b562f9">class</font> combines the <font style="color:#81fd83">fields</font>, <font style="color:#81fd83">properties</font>, <font style="color:#81fd83">events</font> and <font style="color:#81fd83">methods</font>(member function which defines actions) into a single unit.

#### 5. Delegate:

A <font style="color:#b562f9">Delegate</font> is a data structure that refers to a <font style="color:#b562f9">static method</font> or to a <font style="color:#b562f9">class instance</font> and an instance method of that class. It provides a way which tells which method is to be called when an event is triggered.

---
References: [[102.1 Array]], [[102.2 String]], [[102.3 String Builder]], [[102.5 Class]], [[102.6 Delegate]] 