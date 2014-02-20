# Text streams and filters

## Text filtering

### Streams

* stdin
* stdout
* stderr

### Pipes with |

* redirects stdout to stdin

### Outout redirection with <>

* redirects stdout to file
* redirects file content to stdin

### Cat, od and split

#### Cat

* Print content of a file to stdout
* Listen on stdin and output to stdout

#### Od

* Dump files to specified format

 od text # to octal
 od -t c text # to ascii
 od -t x text # to hexadecimal

#### Split

* Split a file using different methods

 split -l 10 text # takes 10 lines of file "text" per new files named "xaa", "xab", ...
 split -b 10 text # split text file into 10bytes files

### Wc, head and tail

* wc: count line/char/bytes/word
* head
* tail (multitail)

### Expand, unexpand and tr

* expand: transform tabs to space (8 default)
* unexpand
* tr: translate from a set to an other

### Pr, nl, and fmt

* Pr: prepare a file for printing -> split in pages and add number, ...
* nl: number line, add the line number at the beginning
* fmt: 

### Sort and uniq

* Sort
* Uniq: remove same and consequtive lines

### Cut, paste, and join

### Sed and awk

### More utils!
