---
title: Automate your monthly journal with a Python script
description:
date: 2026-05-08T15:23:50Z
tags:
   - posts
layout: layouts/post.njk
---

May 8, 2026

I keep a monthly journal in Markdown; one file per month, each entry stamped with the date and time. For a while I was creating those files by hand. That got old fast. So I wrote a Python script to handle it and want to share it with you.

Each time the script runs, it checks whether a journal file for the current month already exists. If it doesn't, it creates one with a header and the first date/time entry. If it does, it just appends a new timestamp so you're ready to write. The file is named by year and month — something like `2026-05  Monthly Journal.md` — and it opens automatically in your editor when it's done.

I run it from [Keyboard Maestro](https://www.keyboardmaestro.com) with a hotkey, but it works just as well from [Alfred](https://www.alfredapp.com) or the command line. Any trigger that can run a script will do.

**To make it work for you, change two things:**

The `JOURNAL_PATH` near the bottom of the script is set to my journal directory. Point it at yours:

```python
JOURNAL_PATH = "/Users/yourname/path/to/journal"
```

The script opens the file in MarkEdit by default. If you use a different editor, swap it out in the `open_in_markedit` function — or just rename the function while you're at it:

```python
subprocess.run(['open', '-a', 'YourEditor', str(file_path)], check=True)
```

Use the app name exactly as it appears in your Applications folder.

Here's the full script:

```python
#!/usr/bin/env python3
"""
Monthly Journal Script
Creates a new monthly journal file each month and appends date/time entries on each run.
Opens the journal in MarkEdit after creating/updating.
"""

import os
import subprocess
from datetime import datetime
from pathlib import Path


def create_or_update_monthly_journal(base_path):
    """
    Creates a new monthly journal or appends to existing one.
    
    Args:
        base_path: Directory path where monthly journals should be stored
    """
    # Ensure the directory exists
    journal_dir = Path(base_path)
    journal_dir.mkdir(parents=True, exist_ok=True)
    
    # Get current date and time
    now = datetime.now()
    year_month = now.strftime("%Y-%m")  # Format: 2026-02
    date_time_str = now.strftime("#### %d %B %Y %I:%M %p")  # Format: #### 01 February 2026 02:14 PM
    
    # Create filename and full path
    filename = f"{year_month}  Monthly Journal.md"
    file_path = journal_dir / filename
    
    # Check if file exists
    if file_path.exists():
        # Append date/time to existing file
        with open(file_path, 'a', encoding='utf-8') as f:
            f.write(f"\n{date_time_str}\n")
        print(f"Appended entry to: {file_path}")
    else:
        # Create new file with header and first date/time entry
        with open(file_path, 'w', encoding='utf-8') as f:
            f.write(f"# {year_month}: Monthly Journal\n")
            f.write(f"{date_time_str}\n")
        print(f"Created new monthly journal: {file_path}")
    
    return file_path


def open_in_markedit(file_path):
    """
    Opens the specified file in MarkEdit.
    
    Args:
        file_path: Path to the file to open
    """
    try:
        # Open file in MarkEdit
        subprocess.run(['open', '-a', 'MarkEdit', str(file_path)], check=True)
        print(f"Opened in MarkEdit: {file_path}")
    except subprocess.CalledProcessError as e:
        print(f"Error opening MarkEdit: {e}")
        print("Make sure MarkEdit is installed in your Applications folder")
    except FileNotFoundError:
        print("Error: 'open' command not found")


if __name__ == "__main__":
    # Path to your journal directory
    JOURNAL_PATH = "/Users/lorenstephens/Writing/Journal"
    
    # Create or update the monthly journal
    journal_file = create_or_update_monthly_journal(JOURNAL_PATH)
    
    # Open in MarkEdit
    open_in_markedit(journal_file)
```

My file is named `monthly_journal.py`. It's not complicated, but it's one less thing I have to think about each month.