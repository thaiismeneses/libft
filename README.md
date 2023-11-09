<p align="center">
  <a href="">
    <img src=" ###" alt="libft">
  </a>
</p>

# Table of Contents
- [Table of Contents](#table-of-contents)
- [0. Description](#0-description)
- [1. Libc functions](#1-libc-functions)
- [2. Additional functions](#2-additional-functions)
- [3. Bonus functions](#3-bonus-functions)
# 0. Description

Write your own library, containing an extract of important functions for your cursus. |

> It is forbidden to declare global variables.
>
> If you need subfunctions to write a complex function, you should define these subfunctions as static to avoid publishing them with your library. It would be a good habit to do this in your future projects as well.
> 
> Submit all files in the root of your repository.
> 
> It is forbidden to submit unused files.
> 
> Every .c must compile with flags.
> 
> You must use the command ar to create your library, using the command libtool is forbidden.

# 1. Libc functions

- isalpha
    
    💡 `int isalpha(int c);`

    checks for an alphabetic character; 
    
- isdigit
    
    💡 `int isdigit(int c);`

    checks for a digit (0 through 9).
    
- isalnum
    
    💡 `int isalnum(int c);`

    checks for an alphanumeric character; it is equivalent to (isalpha(c) || isdigit(c)).
    
- isascii
    
    💡 `int isascii(int c);`

    checks whether c is a 7-bit unsigned char value that fits into the ASCII character set.
    
- isprint
    
    💡 `int isprint(int c);`
    
    checks for any printable character including space.
    
- strlen

    💡 **NAME**
    strlen - calculate the length of a string

    **SYNOPSIS**
    ```C
    #include <string.h>
    size_t strlen(const char *s);
    ```

    **DESCRIPTION**
    The  strlen()  function  calculates  the length of the string pointed to by s, excluding the terminating null byte ('\0').

    
- memset
    
    💡 **NAME**
    memset — fill memory with a constant byte

    **SYNOPSIS**
    ```C
    #include <string.h>
    void *memset(void *s, int c, size_t n);
    ```

    **DESCRIPTION**
    The memset() function fills the first n bytes of the memory area pointed to by s with the constant byte c.

    
- bzero
    
    💡 **NAME**
    bzero, explicit_bzero — zero a byte string

    **SYNOPSIS**
    ```C
    #include <strings.h>
    void bzero(void *s, size_t n);
    ```

    **DESCRIPTION**
    The bzero() function erases the data in the n bytes of the memory starting at the location pointed to by s, by writing zeros (bytes containing '\0') to that area.
    
    
- memcpy
    
    💡 **NAME**
    memcpy — copy memory area

    **SYNOPSIS**
    ```C
    #include <string.h>
    void *memcpy(void *dest, const void *src, size_t n);
    ```

    **DESCRIPTION**
    The  memcpy()  function  copies  n  bytes from memory area src to memory area dest.  The memory areas ***must not overlap***.  Use memmove(3) if the memory areas do overlap.

    
- memmove
    
    💡 **NAME**
    memmove — copy memory area

    **SYNOPSIS**
    ```C
    #include <string.h>
    void *memmove(void *dest, const void *src, size_t n);
    ```
    
    **DESCRIPTION**
    The memmove() function copies n bytes from memory area src to memory area dest.  The memory areas ***may overlap***: copying takes place as though the bytes in src are first copied into a temporary array that does  not  overlap src or dest, and the bytes are then copied from the temporary array to dest.
    
    
- strlcpy
    
    💡 **NAME**
    strlcpy — size-bounded string copying

    **SYNOPSIS**
    ```C
    #include <string.h>
    size_t strlcpy(char *dst, const char *src, size_t size);
    ```
    
    **DESCRIPTION**
    The strlcpy() function copies up to size - 1 characters from the NUL-terminated string src to dst, NUL-terminating the result.
    
    
- strlcat
    
    💡 **NAME**
    strlcat — size-bounded string concatenation

    **SYNOPSIS**
    ```C
    #include <string.h>
    size_t strlcat(char *dst, const char *src, size_t size);
    ```

    **DESCRIPTION**
    The strlcat() function appends the NUL-terminated string src to the end of dst.  It will append at most size - strlen(dst) - 1 bytes, NUL-terminating the result.
    
    
- toupper
- tolower
    
    💡 **NAME**
    toupper, tolower - convert uppercase or lowercase

    **SYNOPSIS**
    ```C
    #include <ctype.h>
    int toupper(int c);
    int tolower(int c);
    ```
    
    **DESCRIPTION**
    These functions convert lowercase letters to uppercase, and vice versa.
    If  c is a lowercase letter, toupper() returns its uppercase equivalent, if an uppercase representation exists in the current locale.  Otherwise, it returns c.
    If  c is an uppercase letter, tolower() returns its lowercase equivalent, if a lowercase representation exists in the current locale.  Otherwise, it returns c.
    If c is neither an unsigned char value nor EOF, the behavior of these functions is undefined.
    
    
- strchr
- strrchr
    
    💡 **NAME**
    strchr, strrchr- locate character in string

    **SYNOPSIS**
    ```C
    #include <string.h>
    char *strchr(const char *s, int c);
    char *strrchr(const char *s, int c);
    ```
    
    **DESCRIPTION**
    The strchr() function returns a pointer to the first occurrence of the character c in the string s.
    The strrchr() function returns a pointer to the last occurrence of the character c in the string s.
    Here "character" means "byte"; these functions do not work with wide or multibyte characters.
    

    
- strncmp
    
    💡 **NAME**
    strcmp, strncmp — compare two strings

    **SYNOPSIS**
    ```C
    #include <string.h>
    int strcmp(const char *s1, const char *s2);
    int strncmp(const char *s1, const char *s2, size_t n);
    ```
    
    **DESCRIPTION**
    The strcmp() function compares the two strings s1 and s2.  The locale is not taken into account (for a locale-aware comparison, see strcoll(3)).  It returns an integer less than, equal to, or greater than zero if  s1  is found, respectively, to be less than, to match, or be greater than s2.
    The strncmp() function is similar, except it compares only the first (at most) n bytes of s1 and s2.
    

    
- memchr
    
    💡 **NAME**
    memchr — scan memory for a character

    **SYNOPSIS**
    ```C
    #include <string.h>
    void *memchr(const void *s, int c, size_t n);
    ```
    
    **DESCRIPTION**
    The  memchr()  function scans the initial n bytes of the memory area pointed to by s for the first instance of c.  Both c and the bytes of the memory area pointed to by s are interpreted as unsigned char.
    
    
- memcmp
    
    💡 **NAME**
    memcmp — compare memory areas

    **SYNOPSIS**
    ```C
    #include <string.h>
    int memcmp(const void *s1, const void *s2, size_t n);
    ```

    **DESCRIPTION**
    The  memcmp()  function  compares the first n bytes (each interpreted as unsigned char) of the memory areas s1 and s2.
    
- strnstr
    
    💡 **NAME**
    strnstr — locate a substring in a string

    **SYNOPSIS**
    ```C
    #include <string.h>
    char *strnstr(const char *big, const char *little, size_t len);
    ```
    
    **DESCRIPTION**
    The strnstr() function locates the first occurrence of the null-terminated string little in the string big,
    where not more than len characters are searched.  Characters that appear after a ‘\0’ character are not searched.  Since the strnstr() function is a FreeBSD specific API, it should only be used when portability is not a concern.
   
    
- atoi
    
    💡 **NAME**
    atoi — convert a string to an integer

    **SYNOPSIS**
    ```C
    #include <stdlib.h>
    int atoi(const char *nptr);
    ```
    
    **DESCRIPTION**
    The atoi() function converts the initial portion of the string pointed to by nptr to int.  The behavior is the same as strtol(nptr, NULL, 10); except that atoi() does not detect errors.
    
- calloc
    
    💡 **NAME**
    malloc, free, calloc,  — allocate and free dynamic memory

    **SYNOPSIS**
    ```C
    #include <stdlib.h>
    void *malloc(size_t size);
    void free(void *ptr);
    void *calloc(size_t nmemb, size_t size);
    ```
    
    **DESCRIPTION**
    The calloc() function allocates memory for an array of nmemb elements of size bytes each and returns a pointer to the allocated memory.  The memory is set to zero.  If nmemb or size is  0,  then  calloc()  returns  either NULL,  or  a  unique  pointer value that can later be successfully passed to free().  If the multiplication of nmemb and size would result in integer overflow, then calloc() returns an  error.   By  contrast,  an  integer overflow  would  not  be detected in the following call to malloc(), with the result that an incorrectly sized block of memory would be allocated: malloc(nmemb * size);
    
    
- strdup
    
    💡 **NAME**
    strdup, strndup, strdupa, strndupa — duplicate a string

    **SYNOPSIS**
    ```C
    #include <string.h>
    char *strdup(const char *s);
    ```
    
    **DESCRIPTION**
    The  strdup() function returns a pointer to a new string which is a duplicate of the string s.  Memory for the new string is obtained with malloc(3), and can be freed with free(3).

    
# 2. Additional functions
- ft_substr

    **SYNOPSIS**
    ```C
    #include <stddef.h>
     char   *ft_substr(const char *s, unsigned int start, size_t len);
    ```
    
    **DESCRIPTION**
    Allocates (with malloc(3)) and returns a substring from the string ’s’. The substring begins at index ’start’ and is of maximum size ’len’.

- ft_strjoin

    **SYNOPSIS**
    ```C
     char   *ft_strjoin(const char *s1, const char *s2);
    ```
    
    **DESCRIPTION**
    Allocates (with malloc(3)) and returns a new string,which is the result of the concatenation of ’s1’ and ’s2’.

- ft_strtrim

    **SYNOPSIS**
    ```C
     char   *ft_strtrim(const char *s1, const char *set);
    ```
    
    **DESCRIPTION**
    Allocates (with malloc(3)) and returns a copy of ’s1’ with the characters specified in ’set’ removed from the beginning and the end of the string.

- ft_split

    **SYNOPSIS**
    ```C
     char   **ft_split(const char *s, char c);
    ```
    
    **DESCRIPTION**
    Allocates (with malloc(3)) and returns an array of strings obtained by splitting ’s’ using the character ’c’ as a delimiter. The array must end with a NULL pointer.

- ft_itoa

    **SYNOPSIS**
    ```C
     char   **ft_itoa(int n);
    ```
    
    **DESCRIPTION**
     Allocates (with malloc(3)) and returns a string representing the integer received as an argument. Negative numbers must be handled.

- ft_strmapi

    **SYNOPSIS**
    ```C
     char   *ft_strmapi(const char *s, char (*f)(unsigned int, char));
    ```
    
    **DESCRIPTION**
     Applies the function ’f’ to each character of the string ’s’, and passing its index as first argument to create a new string (with malloc(3)) resulting from successive applications of ’f’.

- ft_striteri

    **SYNOPSIS**
    ```C
     void   ft_striteri(char *s, void (*f)(unsigned int, char*));
    ```
    
    **DESCRIPTION**
     Applies the function ’f’ on each character of the string passed as argument, passing its index as first argument.Each character is passed by address to ’f’ to be modified if necessary.

- ft_putchar_fd

    **SYNOPSIS**
    ```C
     void   ft_putchar_fd(char c, int fd);
    ```
    
    **DESCRIPTION**
     Outputs the character 'c' to the given file descriptor

- ft_putstr_fd

    **SYNOPSIS**
    ```C
     void   ft_putstr_fd(char *s, int fd);
    ```
    
    **DESCRIPTION**
     Outputs the string 's' to the given file descriptor

- ft_putendl_fd

    **SYNOPSIS**
    ```C
     void   ft_putendl_fd(char *s, int fd);
    ```
    
    **DESCRIPTION**
     Outputs the string 's' to the given file descriptor followed by a newline.

- ft_putnbr_fd

    **SYNOPSIS**
    ```C
     void   ft_putnbr_fd(int n, int fd);
    ```
    
    **DESCRIPTION**
     Outputs the integer 'n' to the given file descriptor.

# 3. Bonus functions

Manipulating lists with a help of the following lstruct to represent a node of yur list. Adding it to libft.h file:

```C
     typeof struct s_list
     {
        void        *content;
        struct s_list   *next;
     }      t_list;
```    
 **DESCRIPTION**
     Content: The data constained in the node.
     void* allows to the store any kind of data.
     next: The address of the next node, or NULL if the next node is the last one.

- ft_lstnew

    **SYNOPSIS**
    ```C
     t_list *ft_lstnew(void *content);
    ```
    
    **DESCRIPTION**
     Allocates (with malloc(3)) and returns a new node. The member variable ’content’ is initialized with the value of the parameter ’content’. The variable ’next’ is initialized to NULL.

- ft_lstadd_front

    **SYNOPSIS**
    ```C
     t_list *ft_lstadd_front(t_list **lst, t_list *new);
    ```
    
    **DESCRIPTION**
     Adds the node 'new' t the beginning of the list.

- ft_lstsize

    **SYNOPSIS**
    ```C
     int    ft_lstsize(t_list *lst);
    ```
    
    **DESCRIPTION**
     Counts the number of nodes in a list.

- ft_lstlast

    **SYNOPSIS**
    ```C
     t_list *ft_lstlast(t_list *lst);
    ```
    
    **DESCRIPTION**
     Returns the last node of the list.

- ft_lstadd_back

    **SYNOPSIS**
    ```C
     void   ft_lstadd_back(t_list **lst, t_list *new);
    ```
    
    **DESCRIPTION**
    Adds the node 'new' t the end of the list.

- ft_lstdelone

    **SYNOPSIS**
    ```C
     void   ft_lstdelone(t_list *lst, void (*del)(void *));
    ```
    
    **DESCRIPTION**
     Takes as a parameter a node and frees the memory of the node’s content using the function ’del’ given as a parameter and free the node. The memory of ’next’ must not be freed.

- ft_lstclear

    **SYNOPSIS**
    ```C
     void   ft_lstclear(t_list **lst, void (*del)(void *));
    ```
    
    **DESCRIPTION**
     Deletes and frees the given node and every successor of that node, using the function ’del’ and free(3). Finally,the pointer to the list must be set to NULL.

- ft_lstiter

    **SYNOPSIS**
    ```C
     void   ft_lstiter(t_list *lst, void (*f)(void *));
    ```
    
    **DESCRIPTION**
     Iterates the list ’lst’ and applies the function ’f’ on the content of each node.

- ft_lstmap

    **SYNOPSIS**
    ```C
     t_list     *ft_lstmap(t_list *lst, void*(*f)(void*), void(*del)(void*));
    ```
    
    **DESCRIPTION**
     Iterates the list ’lst’ and applies the function ’f’ on the content of each node. Creates a new list resulting of the successive applications of the function ’f’.The ’del’ function is used to delete the content of a node if needed.


