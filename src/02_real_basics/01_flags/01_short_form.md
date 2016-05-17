# Short Form

An extremely common version of a flag is known as the *short form*, or *short* for short (sorry). In this form, a single hyphen is used, followed by a single character, such as the `-a` or `-Z` above.

A good example is the very common convention to use the uppercase `V` character as the short form in order to tell a program to print it's version number and then exit.

Try this with `rustc` to see an example.

```
$ rustc -V
rustc 1.8.0 (db2939409 2016-04-11)
```

## Short Form Conventions

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

