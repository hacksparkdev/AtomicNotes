Tags: [[bash]] [[Programming]] [[linux]] 
 Date: 2024-10-13 
 
---

## Source 
---
[Introduction to bash scripting (GitHub)](https://github.com/bobbyiliev/introduction-to-bash-scripting/blob/main/ebook/en/content/006-bash-comments.md)


---


## Description:
Bash (Bourne Again Shell) is a Unix shell and command-line interpreter that is widely used on Linux and macOS systems. It allows users to interact with the operating system by typing commands directly into a terminal or by running scripts. Here’s a more detailed breakdown:

---

## Code Snippet:
Bash files should in .sh

For a bash script to run the first line of code needs to be:
```Terminal 
#!/bin/bash
```

#### Hello World 
```Bash
#!/bin/bash
echo "Hello world"
```

You will need to make the file executable after this.
```Terminal 
chmod +x nameoffile.sh
```

Run the command 
```Terminal 
./nameoffile.sh
```

 You can also run the Command with:
```Terminal 
bash nameoffile.sh
```

