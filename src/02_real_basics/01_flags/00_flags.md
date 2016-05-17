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
