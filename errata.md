# Errata

This file describes inaccuracies, typos, errors in the first edition.

The page number is provided first, then the section number. The sections are
important for those who read the Kindle version, since the page numbers differ
there. 


### Page 4, Section 1.1.2.
* "... description, compared to a ~~calculation model~~ model of computation"

* "a modern computer from the simple schematic in ~~Figure 1-2~~ Figure 1-1".

### Page 6, Section 1.2.3.

"~~zero division~~ division by zero"

### Page 8, Section 1.3. 

"...while main memory uses ~~condensers~~ capacitors"

### Page 35, Section 2.7.

* `read_word` should also return word length in `rdx` when the value
  returned in `rax` is not 0.

* Footnote: 
" Their codes are 0x20, 0x9, and ~~0x10~~ 0xA, respectively."


### Page 45, Section 3.4.1.

"...fills the upper half of a wide register with ~~sign bit~~zero bits!"

### Page 57, Section 4.9.  

"~~Use `print_string` routine...~~": the entire list item should be removed.

### Page 67, Section 5.1.5. 

"... will also accept ~~`rip` and~~ `rflags` register~~s~~."

### Page 141, Section 8.4.2.

"3. as ..." should be "3. * as ..."

### Page 257, Section 13.10.1. 

In the listing `bmp_struct.c`, `struct` keyword should start with a lower case letter.

### Page 266, Section 14.1.2.

"It means that the ~~last~~ first argument __after those passed in registers__ will be on top of the stack before the call is performed."

Example:

```c
int f(int, int, int, int, int, int, int, int, int, int);

...
f(1,2,3,4,5,6,7,8,9,10);
```

The call of `f` will be translated as follows:

```asm
push       10 
push        9
push        8
push        7
mov    r9,  6
mov    r8,  5
mov    rcx, 4
mov    rdx, 3
mov    rsi, 2
mov    rdi, 1 
```

### Page 267, Section 14.1.2.

An important addition for the third item: when `call` is executed, the stackshould be 16-bit aligned. Some compiled functions will count on that. 

### Page 268, Section 14.1.3.

`maximum.c` should be compiled with `-fno-stack-protector` flag. [Related discussion](https://github.com/Apress/low-level-programming/issues/28)

### Page 303, Section 15.6

"4. Defined in dynamic library and used globally.

~~Should be a part of linked list item rather than a paragraph on its own.~~ This is also done by using GOT (and PLT for functions)."
