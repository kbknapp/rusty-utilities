# More than a Boolean

As I said before, there is actually another bit of data flags can pass to the program, vice just their presence and that's the number of times they're used. Some programs allow for a single flag to be used more than once, a common example is the `--verbose` or `-v` flag of many programs. In the case of `--verbose`, it usually means, "The more times it's passed, the more verbose the output gets." i.e.

```
$ program --verbose
```

Means "verbose output", whereas

```
$ program --verbose --verbose
```
Means "very verbose output" and so on, and so forth.

Notice typing the long form multiple times isn't super pleasant. Here using the short form is far easier

```
$ program -v -v
```

Or the even nicer

```
$ program -vv
```

Which would you rather type?
