Simple C Console Library Management System

One-line description
--------------------
A simple console-based C Library Management System that stores books and issued-book records in local files (`books.txt`, `issue.txt`) and supports adding, listing, removing, and issuing books.

What this project does
----------------------
- Lets you add books (id, title, author, date added).
- Lists all available books.
- Removes a book by id.
- Issues a book to a student (records student name, class, roll, book, date).
- Lists all issued books.

Key files
---------
- `project_Lib.c` — main source implementing the console menu and functionality.
- `project_Lib.exe` — compiled executable (if provided in repo).
- `books.txt` — binary file used to persist book records (created at runtime).
- `issue.txt` — binary file used to persist issued-book records (created at runtime).

How to build (Windows / PowerShell)
-----------------------------------
There are two common ways to build on Windows. Use whichever toolset you have installed.

- With GCC (MinGW / MSYS):

```powershell
# compile (PowerShell)
gcc project_Lib.c -o project_Lib.exe -std=c11 -Wall -Wextra
```

Note: the source uses `getch()`; if you get an undefined reference you may need to add `#include <conio.h>` to `project_Lib.c` or link against a compatibility library.

- With Microsoft Visual C++ (Developer Command Prompt):

```powershell
# open "Developer Command Prompt for VS" then run:
cl /Fe:project_Lib.exe project_Lib.c
```

How to run
----------
From the project directory in PowerShell run:

```powershell
# run the program
.\project_Lib.exe
```

When you run it, follow the on-screen menu to add/list/remove/issue books. The program creates/updates `books.txt` and `issue.txt` in the same directory.

Important notes and caveats
--------------------------
- The program stores records in binary format using `fwrite`/`fread`. `books.txt` and `issue.txt` are not plain text and should not be edited by hand.
- The source uses unsafe/obsolete functions such as `gets()` and `fflush(stdin)` which are undefined/unsafe in standard C. For security and portability replace `gets()` with `fgets()` and handle input trimming.
- `getch()` and `system("cls")` and `system("color")` are platform-specific. The program is targeted at Windows consoles.
- Input validation is minimal; invalid or duplicate IDs may cause unexpected behavior.

Small improvement ideas
-----------------------
- Replace `gets()` with `fgets()` and implement safe input parsing.
- Use a text-based format (CSV/JSON) for easier debugging and portability, or add file-format versioning.
- Add search and update functionality for books and a return-book feature.
- Move file I/O into separate functions and add unit tests for the data layer.

License
-------
No license file is included. Add a LICENSE if you want to clarify reuse terms.

Contact / Next steps
--------------------
If you want, I can:
- Add a safer input wrapper (replace `gets()` with `fgets()`),
- Add a `Makefile` or PowerShell build script, or
- Convert the persistent storage to a human-readable CSV.

