Status: 
Tag: #UserInput #IO #ReadLine #Read #ReadKey
Links: [[106 Methods]]

---
> [!note] 
>  # User Input

In C#, user input can be obtained using the Console class, which provides various methods for reading input from the user through the console.

## ReadLine()

This method reads a line of text from the console and returns it as a string. The user can type any sequence of characters followed by the enter key, and the entire line will be returned as a string.

``` run-csharp
Console.WriteLine("Enter your name:");
string name = Console.ReadLine();

Console.WriteLine("Hello, " + name + "!");
```

## Read()

This method reads the next <font style="color:#81fd83">characte</font>r from the console input stream and <font style="color:#81fd83">returns</font> it as an <font style="color:#81fd83">integer</font> value. The returned value is the ASCII code of the character.

``` run-csharp
Console.WriteLine("Enter a character:");
int asciiValue = Console.Read();

Console.WriteLine("You entered: " + asciiValue);

```

## ReadKey()

This method reads the <font style="color:#81fd83">next key</font> or function key pressed by the user and returns it as a ConsoleKeyInfo object, which contains information about the key pressed, such as the <font style="color:#81fd83">key code</font> and <font style="color:#81fd83">modifier keys</font> (such as Shift or Ctrl).

``` run-csharp
Console.WriteLine("Press any key to continue...");
ConsoleKeyInfo keyInfo = Console.ReadKey();

Console.WriteLine("You pressed the key: " + keyInfo.Key);

```

---
References: