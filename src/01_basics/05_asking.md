# Asking and Prompting

Asking for, or prompting for the information is an acceptable way in some circumstances, but can get annoying and tedious for the user *very* quickly. Also, all input from the user needs to be parsed, and/or sanitized in some manner.

Back to `wc` it could look something like:

```
$ wc
File to count?: evil.txt
 4 26 221 evil.txt
```

There are very big drawbacks associated with asking or prompting. First, this is a terrible method when there are multiple pieces of information that are required intermixed with pieces that are optional.

If you ask for information, especially optional information, ensure your ordering and grouping is correct. There is almost nothing more frustrating than hitting `[enter]` one too many times, missing a value and having to repeat the entire invocation, including values one has already entered.

Asking for information also precludes your program from being included in most scripts. Imagine if `wc` asked for the file, but you wanted to run `wc` across every file in a directory? That would be terrible.

There are however times when asking may be an acceptable method. If advanced instructions need to be included between bits of information, or if a program is designed to only be invoked a single time ever (or perhaps with large gaps of time between invocations), or most importantly/commonly if these pieces of information build upon each other where actions must take place between each question, and the answer is derived from the output of the last question.

Unless the application, or one of it's modes, falls generally into one of those categories there are usually better options than prompting. While prompting may seem more user friendly at first, it quickly gets irritating.
