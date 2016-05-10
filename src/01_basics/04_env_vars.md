# Environmental Variables

Using environmental variables is perhaps the easiest. All it requires programatiically is checking for said variable, reading it's value, and done. The tricky part comes in what to do when the value or variable isn't present.

Also, because there's no namespacing, people tend to use things like, `XDG_CURRENT_DESKTOP`, but imagine trying to set something like that with every invocation of a utility! It'd be a nightmare. Imagine if `wc` did this:

```
$ WC_FILE_TO_COUNT=evil.txt wc
 4 26 221 evil.txt
```

Environmental variables are best left to information that doesn't change often, needs to be shared between programs, or perhaps is private in some manner. They are also decent for optional settings, which are unlikely to be used, or only in a very specific niche circumstance. Such as something like `rustc`'s backtrace setting (`RUST_BACKTRACE`).

This isn't an all inclusive list by any means, but it's good enough for today. Therefore, let's continue on our merry way!
