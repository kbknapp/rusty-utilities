# Long Form

The *long form* or *long* for short (sorry again), is just as common as the short form. The long form typically preceded by two hyphens `--` and one or more (usually more) characters. `--flag` was the example given above. The long form is often used because it says a little more about the flag *to the user*.

This is a very important note, and the first time we've seen it thus far. While designing a CLI, it's often helpful to think *as the user* rather than as the program. I can't stress this enough. Seeing that a program should be invoked as, `program -e` probably doesn't convey much about what that flag is doing. But seeing `program --exclude-directories` says far more.

This is why you'll often see the long form used in conjunction with the short form in order to say the same thing, or pass the same data to the program.

An example would be the convention of using `--version` to tell a program to print it's version and exit (just like `-V`). Again, we turn to `rustc` for the example:

```
$ rustc --version
rustc 1.8.0 (db2939409 2016-04-11)
```

Notice it does the exact same thing as `-V`, only as the user `--version` is far easier to remember than `-V`...at least at first until you've used it several times. At which point, the short form becomes handy, because it's far quicker to type `-V` than it is the long form.

In fact, if we view the help documentation of `rustc` (which can be accessed by passing another flag `--help`) we'll actually see the short and long form listed together:

```
$ rustc --help
 # [...]
    -V --version        Print version info and exit
 # [...]
```

## Long Form Conventions

It's usually a good idea to use only lower-case characters when thinking of long form flags. Of course, there may be times when it's appropriate to have an upper-case character, but this should be the exception and not the rule.

It's also possible to have compound, or multiple words in a long form flag, although one must use a character other than a space as the separator. It's convention to use the hyphen character.

Prefer

```
$ program --compound-word
```

Over

```
$ program --compound_word
```

Long form flags should be as short as possible, but not so short that they lose meaning. The entire point of having a long form is to convey more meaning. Although an arbitrary limit, I try to use no more than three words in a compound long form flag, and only if those words are short, otherwise I'll limit myself to two words.

When using the long form in conjunction with a short form, although not required, it's a good idea to use the first character of the long form, as the short form. This makes the correlation easier to remember.

Keep in mind, this isn't always possible because there are times where several long form flags share a common first character.

For example there is a very common long form flag `--verbose` on many command line applications. In fact, `rustc` again uses this convention. If one wanted both `--version` and `--verbose` to have a short form, which one should get the `-v`?!

In these cases, it's customary to change the case of the short form, not the long form. OK, so now we know there should be `-v` for one of them,  and `-V` for the other. But that still doesn't solve which one gets which. This is somewhat subjective, but being that the lower-case form is easier to type, it should go to the flag which has the most potential for use, or the more common case.

In `rustc` the authors decided, to which I agree, that `--verbose` is far more likely to be used, than `--version`. If we view the help documentation we see that is how they divided up the short forms.

```
$ rustc --help
 # [...]
    -V --version        Print version info and exit
    -v --verbose        Use verbose output
```

Remember way back when I said there was a limited number of short forms a flag could take? If a program has a large number of flags, not every flag needs a short *and* long form. Not all long forms need to share a character with the short form. In fact, not all flags even need a short form (which is arguably the more limited form).


