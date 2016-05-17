# Tools of the trade

One last aside before we get to the tools, I promise. This one is short, but needs to be said.

Let's first think about why these tools exist, and what it is we're trying to accomplish by using them. If you said, they exist to communicate with the program, then you're correct. Also, some may say that using these tools is a way to pass data to a program. Both are true.

All of these tools, be it flags, options, sub-commands, etc. they're all in order to pass data and communicate to the program. Sounds simple, no? The difficult part is how to use these tools in order to be efficient, and intuitive about passing the data to the program. We don't want to cause unnecessary strain on the user, or increased mental load simply because our interface wasn't well designed or well thought out.

Throughout the next few pages we'll see some common pitfalls, and how to best utilize these tools in order to pass data in the most efficient manner possible.

Try and keep this in the back of your mind while designing any CLI, or while reading through this chapter, "What do I want to know from the user, and how can they best tell me?"

## Conventions

It should go without saying, but just to cover all the bases and not to insult anyone's intelligence when speaking about these tools and arguments in general, I mean all those words, symbols, and characters typed after the program name at the command line. Such as

```
$ program --foo bar baz -QuX
```

Here, the dollar sign (`$`) simply denotes a user's terminal prompt, the program is called `program` and all the arguments are `--foo bar baz -QuX`. Throughout the next few pages, and even the rest of the book, the very first word to follow the dollar sign is the program name, unless I denote otherwise.
