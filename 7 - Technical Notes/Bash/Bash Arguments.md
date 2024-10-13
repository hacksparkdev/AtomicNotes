Tags: [[bash]] [[linux]] [[IT]] [[Programming]] [[Cyber Security]]  [[arguments]] 
 Date: 2024-10-13 
 
---

## Source:
[Introduction to bash scripting (GitHub)](https://github.com/bobbyiliev/introduction-to-bash-scripting/blob/main/ebook/en/content/006-bash-comments.md)

---

## Description:
You can pass arguments to your shell script when you execute it. To pass an argument, you just need to write it right after the name of your script

---

## Code Snippet:

Lets show an example to show how to reference arguments:
```Bash
#!/bin/bash

echo "Argument one is $1"
echo "Argument three is $3"
echo "Argument 2 is $2"
```

Now in the terminal: 
```Terminal 
./nameofscript.sh dog cat bird
```

This will add the arguments we passed to the the script in the order we passed them. 
```Termnal
Argument one is dog
Argument three is bird
Argument two is cat
```

