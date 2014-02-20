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

### Expand, unexpand and tr

### Pr, nl, and fmt

### Sort and uniq

### Cut, paste, and join

### Sed and awk
