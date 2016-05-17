# Flags

We'll start with the simplest form of argument, the *flag*. In argument parsing parlance, the flag is a boolean. It's either present, or it's not. Flags typically start with either a single, or double *hyphen* character (`-`, or `--` respectively) and are followed by one or more characters. The hyphen is often called a *tac* or *dash* as well.

Some example flags are:

```
-a
-Z
--flag
-flag
```

Here we have four flags, `-a`, `-Z`, `--flag`, and `-flag` taking up the four most common forms a flag can take. We'll take a look at the different forms shortly.

Remember talking about, "What data is the user trying to pass?" Well when it comes to flags, they're quite simple. The only data that it passes to the program is it's presence, or lack there of.

Actually, that's not *quite* true. There is another form of data a flag can pass to the program. Can you guess what it is? It's the number of occurrences. Some flags can be present multiple times, which can relay to the program a little bit more information than simply being present or not. We'll speak about this in a bit.

First, let's take a look at the different forms of flags.

## Short Form

An extremely common version of a flag is known as the *short form*, or *short* for short (sorry). In this form, a single hyphen is used, followed by a single character, such as the `-a` or `-Z` above.

A good example is the very common convention to use the uppercase `V` character as the short form in order to tell a program to print it's version number and then exit.

Try this with `rustc` to see an example.

```
$ rustc -V
rustc 1.8.0 (db2939409 2016-04-11)
```

### Short Form Conventions

First, prefer lower-case characters to upper case. In most languages, an upper-case character requires an additional key to be pressed.

Prefer

```
$ program -a
```

To

```
$ program -A
```

There is an exception to this guidance that we'll see in just a minute.

The second thing to consider, is the language of keyboard your program is most likely to be used with. If your program is region specific to a certain area of the world, where a particular keyboard is common, pick characters that only require a single key press to achieve. If possible, and the language allows, prefer ASCII characters to unicode characters. If the program is not designed to be used in parts of the world with Western Latin character sets (such as English), this point can safely be ignored. If there is a possibility for the program to be used in areas with Western Latin character sets, it's common for the keyboard keyboards to ship with only a limited (if any) unicode support. ASCII is a safe bet.

Finally, one should acknowledge that there is a relatively small number of possibilities for the short form of a flag. Especially in ASCII only contexts. We'll come back to this note after we talk about the *long form*.

## Long Form

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

### Long Form Conventions

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

### Combining Long and Short Forms

Attempt to prioritize common flags, or flags which you believe will be used the most. The prioritization I use is, from most use, to least use:

 * Both long and short form, short form has a shared lower-case character
 * Both long and short form, short form has a shared upper-case character
 * Both long and short form, short form has non-shared lower-case character
 * Both long and short form, short form has a non-shared upper-case character
 * Long form only
 * Short form only, lower-case character
 * Short form only, upper-case character

It's also a good practice to do a little forward thinking and try to reserve short forms for common flags you may not have implemented yet, but intend to. Adding a short form to a later version doesn't break backwards compatibility, but changing or removing a short form of a flag *does* break it, and can dampen ones reputation in the worst case.

## Alternate Long Forms

There is another version of the long form, which uses a single hyphen followed by two or more characters. In the example *all* the way the top, `-flag` was used. This form is far less common today, but still appears from time to time. We won't spend much time talking about this form, and in fact I would recommend avoiding it all together. This is because it's mutually exclusive with the next item on our list, which in my opinion is far more useful and common.

## Combining Short Forms

This is not really a form, but a decently common convention supported by many CLIs. It allows short form flags to be combined with only a single hyphen, instead of having to re-type the hyphen (and a space) with each one. An example would be

```
$ program -aZBd
```

Being the equivalent of

```
$ program -a -Z -B -d
```

While this form may not look super readable, when using many flags it's far nice to type. Especially, consider if each of those flags only had long forms! Yuck. Again, this isn't always supported, but I'd suggest giving it some thought as it can make the end user experience that much nicer. The main thing to consider is that, like stated above, it doesn't work when the alternate long form is desired. Otherwise `-flag` would be ambiguous as to whether or not it should be parsed as a long or form, or as `-f -l -a -g`.

## The Final Bit of info

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

## What Are You Trying to Say?!

The final thing to consider with flags is what information you're trying to get from the user. Should the flag be the user telling the program a special case is present, a special case is *not* present, or do a particular task?

Unfortunately there isn't a standard answer for this. The best thing I can say, is to simply put a lot of thought into whether you want the flag to be *positive* or *negative*.

A *positive* flag tells the program of a particular task, or condition. Whereas a *negative* flag tells the program of the *lack* of a particular task or condition.

Usually, although not always, positive flags are good for common case scenarios, and negative flags are good for exception case scenarios.

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
