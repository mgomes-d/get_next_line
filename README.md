# get_next_line

The `get_next_line` function is a utility function designed to read a line from a given file descriptor (fd) in C. It is particularly useful for reading text from files or other input streams, such as standard input (stdin).

## Introduction

The `get_next_line` function is a popular project at 42 School and other C programming contexts. It allows you to read a line from a file descriptor and handles memory allocation and management for you. This function is especially valuable when you need to process input line by line, such as reading configuration files or parsing textual data.

## Usage

To use the `get_next_line` function in your C program, you need to include the header file `get_next_line.h`, and you should have the implementation in a source file, such as `get_next_line.c`. The function takes an integer file descriptor (fd) as its only argument and returns a pointer to a line read from that file descriptor.

Here's an example of how to use the `get_next_line` function:

```c
#include "get_next_line.h"

int main() {
    int fd = open("example.txt", O_RDONLY);
    char *line;

    while ((line = get_next_line(fd)) != NULL) {
        // Process the line
        printf("%s\n", line);

        // Don't forget to free the line when you're done
        free(line);
    }

    // Close the file descriptor
    close(fd);

    return 0;
}
```
## Compilation

To compile your program using the get_next_line function, you need to include the necessary files and set the buffer size for reading lines. Use the -D BUFFER_SIZE=n flag to define the buffer size. For example:
```sh
cc -Wall -Wextra -Werror -D BUFFER_SIZE=19 main.c get_next_line.c -o my_program
```

## Norm and Requirements

Make sure to follow the norm and requirements specified in your project guidelines. Handle memory allocation properly, free allocated memory, and ensure your code is modular and well-organized.

## Author
This project was completed as part of the common-core at 42 School by Murillo Gomes De Senna.

