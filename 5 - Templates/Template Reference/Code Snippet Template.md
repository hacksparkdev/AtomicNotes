# {{Title of the Code Snippet}}

## Date: {{date}}

---

## Description:
- Brief description of what this snippet does and when you might use it (e.g., “Bash script for automating Elasticsearch backup process”).

---

## Code Snippet:
```bash
#!/bin/bash
# Elasticsearch backup script
curl -X PUT "localhost:9200/_snapshot/my_backup/snapshot_1?wait_for_completion=true"
