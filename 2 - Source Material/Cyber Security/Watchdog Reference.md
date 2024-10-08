
### Tutorial: **Getting Started with Watchdog in Python**

---

### Step 1: **Install Watchdog**

First, install the `watchdog` library using pip:

```bash
pip install watchdog

```

---

### Step 2: **Basic Concepts**

Watchdog uses two primary components:
2024-10-06 10:06

status:

Tags:

## Watchdog

References

2024-10-06 10:06

status:

Tags:

## Watchdog

References


- **Observer**: Watches directories or files for changes.
- **Event Handler**: Defines what happens when specific events (like file creation, modification, deletion) occur.

---

### Step 3: **Basic Structure of a Watchdog Script**

Here is the basic structure:

```python
from watchdog.observers import Observer
from watchdog.events import FileSystemEventHandler
import time

# 1. Create an event handler by subclassing FileSystemEventHandler
class MyHandler(FileSystemEventHandler):
    def on_created(self, event):
        print(f"File created: {event.src_path}")

    def on_modified(self, event):
        print(f"File modified: {event.src_path}")

    def on_deleted(self, event):
        print(f"File deleted: {event.src_path}")

# 2. Set up an Observer
observer = Observer()
event_handler = MyHandler()

# 3. Schedule the observer to monitor a directory
observer.schedule(event_handler, path=".", recursive=True)

# 4. Start the observer
observer.start()

try:
    while True:
        time.sleep(1)  # Keep the script running
except KeyboardInterrupt:
    observer.stop()  # Stop the observer if interrupted

observer.join()  # Wait for the observer to finish

```

### Explanation:

- `FileSystemEventHandler`: Handles events like file creation, modification, and deletion.
- `Observer`: Watches a directory for changes.
- The observer is started and runs indefinitely, checking the directory you specify.

---

### Step 4: **Creating a Simple Event Handler**

Let's break down the event handler, where you define how the system reacts to specific events:

```python
from watchdog.events import FileSystemEventHandler

class MyHandler(FileSystemEventHandler):
    # Handles when a file is created
    def on_created(self, event):
        print(f"File created: {event.src_path}")

    # Handles when a file is modified
    def on_modified(self, event):
        print(f"File modified: {event.src_path}")

    # Handles when a file is deleted
    def on_deleted(self, event):
        print(f"File deleted: {event.src_path}")

    # Handles when a file is moved
    def on_moved(self, event):
        print(f"File moved from {event.src_path} to {event.dest_path}")

```

### Explanation:

- **`event.src_path`**: This provides the path of the file where the event occurred.
- You can handle different events (`on_created`, `on_modified`, etc.) based on your needs.

---

### Step 5: **Setting up an Observer**

Now, let’s set up an observer that monitors a directory and calls the event handler when a file system event happens.

```python
from watchdog.observers import Observer
import time

# Create an observer
observer = Observer()

# Set up your event handler
event_handler = MyHandler()

# Schedule the observer to watch a directory (current directory in this case)
observer.schedule(event_handler, path=".", recursive=True)

# Start the observer
observer.start()

# Keep it running until stopped
try:
    while True:
        time.sleep(1)  # Keep the observer running indefinitely
except KeyboardInterrupt:
    observer.stop()  # Stop the observer on keyboard interrupt

# Wait for the observer to stop
observer.join()

```

### Explanation:

- **`observer.schedule(event_handler, path=".", recursive=True)`**: This tells the observer to watch the current directory (`"."`) and all its subdirectories (`recursive=True`).
- **`observer.start()`**: Starts the observer to begin monitoring.
- **`try-except` block**: Keeps the observer running until you stop it manually (Ctrl+C).

---

### Step 6: **Running the Script**

Once you run the script, it will monitor the specified directory for events. Every time a file is created, modified, deleted, or moved, the event handler will trigger, and the corresponding event will be logged.

For example, if you create a file, you’ll see an output like:

```
File created: ./new_file.txt

```

If you delete the file:

```
File deleted: ./new_file.txt

```

---

### Advanced Features (Optional Enhancements):

1. **Monitoring Specific File Types**: You can modify the event handler to monitor specific file types like `.txt` or `.log` files:
    
    ```python
    def on_created(self, event):
        if event.src_path.endswith(".txt"):
            print(f"Text file created: {event.src_path}")
    
    ```
    
2. **Logging Events to a File**: Instead of printing to the console, you can log events to a file:
    
    ```python
    import logging
    
    logging.basicConfig(filename='file_changes.log', level=logging.INFO)
    
    def on_created(self, event):
        logging.info(f"File created: {event.src_path}")
    
    ```
    
3. **Running the Observer in a Thread**: You can run the observer in a separate thread so it doesn’t block the main program:
    
    ```python
    observer.start()  # Run it in the background thread
    observer.join()   # Wait for the observer thread to finish
    
    ```
    

---

This tutorial should give you a strong foundation to start using **Watchdog** for file system monitoring. Let me know if you need help with any specific parts or further customization!