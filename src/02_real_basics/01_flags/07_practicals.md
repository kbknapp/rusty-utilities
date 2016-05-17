## Practical Examples

Of course, this all sounds quite abstract. Imagine we were building `wc`, except let's call it `rwc` since we're talking about Rust. Keep in mind I'm demonstrating examples, and these may not be good uses of flags for `rwc`, but they'll get the point across :)

A use of a positive flag could be for the type of count to be performed, bytes, lines, or words. Imagine a help documentation for `rwc` that looked like,

```
$ rwc --help
 # [...]
    -b, --bytes    print the number of bytes
    -w, --words    print the number of words
    -l, --lines    print the number of lines
```

Usage of `rwc` could look like,

```
$ rwc evil.txt --lines
 4 evil.txt
$ rwc evil.txt --words -b
 26 221 evil.txt
$ rwc evil.txt -lwb
 4 26 221 evil.txt
```

A use of negative flags could be to tell `rwc` *not* to print the file name

```
$ rwc --help
 # [...]
    --no-print-file
$ rwc -lwb --no-print-file evil.txt
 4 26 221
```
