# Get Next Line

### ↪️ Reading Lines
This project involves coding a function that get a line read from a file descriptor.

## Technologies Used
![C](https://img.shields.io/badge/_-C-555555.svg?style=for-the-badge)
![MAKEFILE](https://img.shields.io/badge/_-MAKEFILE-427819.svg?style=for-the-badge)

## Subject
### Mandatory
()

### Bonus
(파일디스크립터를 여러개 다룰 수 있어야함)

## Getting Started
```shell
git clone https://github.com/niamu01/get_next_line
cd get_next_line
gcc -Wall -Wextra -Werror -D BUFFER_SIZE=42 <files>.c
```
> 💡 A buffer size of 42 is used as an example

## How To Use
The `int get_next_line(int fd, char **line)` function can be utilized not only within the main function for testing purposes but also within other parts of your program.

Parameter:
- fd: file descriptor of the file to read from
- line: the value of what has been read

Return:
-	1 : A line has been read
- 0 : EOF has been reached
- -1 : An error happened

### Example:
```c
#include <stdio.h>

int main(void) {
	int fd = open("FILE_NAME", O_RDONLY);
	char *line;
	int	ret;

	while ((ret = get_next_line(fd, &line)) > 0) {
		printf("Line read: %s\n", line);
		free(line);
	}
	
	if (ret == 0)
		printf("End of file reached\n");
	else if (ret == -1)
		printf("An error occurred\n");
	
	return 0;
}
```
