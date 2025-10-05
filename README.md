
DigitalLibrarySystem
=====================

Overview
--------
DigitalLibrarySystem is a small, console-based Library Management application written in C for Windows. It provides basic functionality to add, list, remove, and issue books, persisting records to local files.

Features
--------
- Add a book (id, title, author, date added)
- List all available books
- Remove a book by id
- Issue a book to a student (student name, class, roll, book, date)
- List all issued books

Repository contents
-------------------
- `project_Lib.c` — main program source file
- `project_Lib.exe` — pre-built executable (may be present)
- `books.txt` — binary file containing book records (created at runtime)
- `issue.txt` — binary file containing issued-book records (created at runtime)

Build (Windows)
---------------
Use one of the methods below depending on your toolchain.

With GCC (MinGW / MSYS):

```powershell
gcc project_Lib.c -o project_Lib.exe -std=c11 -Wall -Wextra
```

With Microsoft Visual C++ (Developer Command Prompt):

```powershell
cl /Fe:project_Lib.exe project_Lib.c
```

Run
---
From the project directory:

```powershell
.\project_Lib.exe
```

Notes and limitations
---------------------
- The program uses binary file I/O (`fwrite`/`fread`) — `books.txt` and `issue.txt` are not human-readable.
- The code contains unsafe input functions (`gets()` and `fflush(stdin)`) and minimal input validation. These should be replaced for production use.
- The program uses Windows-specific APIs (`getch()`, `system("cls")`, `system("color")`) and is intended for Windows consoles.

License
-------
No license is included. Add a LICENSE file to specify reuse terms.

