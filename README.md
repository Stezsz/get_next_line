# get_next_line – 42 School Project

`get_next_line` is a project where the objective is to write a function that returns a line from a file descriptor.
The function should read the file descriptor until it encounters a newline (`\n`) or reaches the end of the file (EOF).
This project challenges the student to work with **file handling**, **buffers**, and **memory management**.

---

## Main Objectives

- Implement a function that reads a line from a file descriptor.
- Handle files, file descriptors, and buffers efficiently.
- Use dynamic memory management to handle strings of arbitrary length.
- Ensure that the solution works with both small and large files.
- Handle edge cases like empty lines, multiple newlines, or end-of-file.

---

## Functionality

The function should work as follows:

- **get_next_line**: Reads a line from the given file descriptor and returns it.
- The function will store the file's data in a static buffer and use it to fetch each line.
- The buffer is dynamically allocated and reused to store data between calls to **get_next_line**.

---

## Technical Requirements

- The function must read a line from the file descriptor without using `read` or `write` directly in the main code.
- You must not use the standard `getline` function.
- Memory management should be handled correctly without leaks.
- A working `Makefile` must be provided for compiling the project.
- Code must follow the **42 Norm (Norminette)**.

---

## Example Usage

```c
#include "get_next_line.h"
#include <fcntl.h>
#include <stdio.h>

int main(void)
{
    int fd = open("example.txt", O_RDONLY);
    char *line;

    while ((line = get_next_line(fd)) != NULL)
    {
        printf("Line: %s", line);
        free(line);
    }
    close(fd);
    return (0);
}
```

---

## 📘 Conclusion

`get_next_line` is an essential exercise in handling file I/O, memory management, and dynamic buffers in C.
This project teaches how to read and manage data efficiently from files and ensures the ability to handle edge cases and manage memory properly.

---

> ✅ **Final Grade: 125/100**
> Project made at [42 Lisboa](https://www.42lisboa.com/pt/)
> 👤 Author: Stephan Rodrigues Lassaponari ([@Stezsz](https://github.com/Stezsz))
