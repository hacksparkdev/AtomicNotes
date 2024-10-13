Tags: [[bash]] [[Programming]] [[IT]] [[variables]] [[linux]] [[Cyber Security]]
 Date: 2024-10-13 
 
---

### Source
---
[Introduction to bash scripting (GitHub)](https://github.com/bobbyiliev/introduction-to-bash-scripting/blob/main/ebook/en/content/006-bash-comments.md)


---

## Description:
As in any other programming language, you can use variables in Bash Scripting as well. However, there are no data types, and a variable in Bash can contain numbers as well as characters.

---

## Code Snippet:

Assign a variable with the `=` sign.
```Shell
name="Corey Jones"
```

> Note you cannot have a space before or after the `=` sign

To reference a variable use the `$` : 
```Bash
echo $name
```

Using a variable in a print statement:
```Bash
#!/bin/bash
name="Corey"
echo "Hi there $name" 
```

This will print:
```Terminal 
Hi there Corey
```

We can add variables from the command line by adding `$1` This would be the first input. If we wanted to add more we could `$2` and so on. Or you could use `$@` to read all inputs. 

Example:
```Bash
#!/bin/bash
echo "Hello, $1"
```

In the terminal:
```Termianl 
./nameoffile.sh Corey
```

This would print:
```Termianl 
Hello, Corey
```