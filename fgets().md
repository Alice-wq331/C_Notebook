### fgets()
1. Defined in header <stdio.h>
2. Prototype/Format: 
   ```C
   char *fgets(char *str, int count, FILE *stream);
    ```
    *Reads at most count-1 characters from the given file stream and stores them in the character array pointed to by str <br>
    *Parsing stops if end-of-file occurs or a newline character is found, in which case str will contain that newline character. If no errors occur, writes a null character at the position immediately after the last character written to str.
    <br>
    *The behavior is undefined if count is less than 1.        
3. Return Value:
   *str on success, null pointer on failure.
   <br>

    *If the failure has been caused by end-of-file condition, additionally sets the eof indicator (see feof()) on stream. The contents of the array pointed to by str are not altered in this case.
    <br>
    *If the failure has been caused by some other error, sets the error indicator (see ferror()) on stream. The contents of the array pointed to by str are indeterminate (it may not even be null-terminated).

#### Examples:
```c
FILE* tmo=tmpfile();
fputs("Alan Turing\n", tmpf);
fputs("John von Neumann\n", tmpf);
fputs("Alonzo Church\n", tmpf);

rewind(tmpf);

char buf[8];
while (fgets(buf, sizeof buf, tmpf) != NULL){
        printf("\"%s\"\n", buf);
}

```
```c
char str[10];
count=10;
fgets(str,count,stdin);
```