Tags: [[bash]] [[Programming]] [[IT]] [[user_input]] [[linux]] [[Cyber Security]]
 Date: 2024-10-13 
 
---

## Source
[Introduction to bash scripting (GitHub)](https://github.com/bobbyiliev/introduction-to-bash-scripting/blob/main/ebook/en/content/006-bash-comments.md)

---

## Description:


---

## Code Snippet:

Ask the user for input
```Bash
#!/bin/bash
echo "What is your Name: "
read name

echo "Hi, $name"

echo "Welcome to Hell!!"
```

This will output:
```Termial 
What is your Name?
Corey
Hello, Corey
Welcome to hell!!

```

We can make the line shorter by using the `-p` flag: 
```Bash
#!/bin/bash

read -p "What is your name? " name

echo "Hello, $name"

```
This will produce the same result as above. 

