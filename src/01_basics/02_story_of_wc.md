# The story of wc

Many have heard of the common utility `wc`, but few know it's humble beginnings. We know that today `wc` counts the lines, bytes, or words contained in a file. I assume that when the authors of `wc` set out to write their program, perhaps it was because they had a particular file in mind which was in desperate need of counting, I'll also imagine this file was called `unknown.txt`.

So they set out to write a utility to count the lines, words, and bytes of `unknown.txt`. Several fortnights passed with missed weekends and birthdays, but it all was worth it in the end. `wc` was born. Sure enough, the program diligently spit out the number of lines, words, and bytes and all rejoiced.

I happen to have a historical recount of that initial run. It looked as follows:

```
$ wc
 6 13 104 unknown.txt
```

Some time later, there came another file, `evil.txt` which was in desperate need of counting. The lead developer said, "This is no issue, we'll change the source in a jiffy, re-compile, and that evil file who's count was unknown would be a mystery no more!" Sure enough, after a quick change of the code, the dutiful `wc` spit out the number of lines in `evil.txt`.

```
$ wc
 4 26 221 evil.txt
```

Again, there was peace in the land. Although, again this peace was short lived.

The lead developer grew tired of constantly changing the source code, and re-compiling each time she found a new file to count. "There has to be a better way." She exclaimed in agony.

After many sleepless afternoons pondering her woes she determined life would be grand again if only little `wc` could get this vital piece of information at runtime, for there was no way know such things before. The lead developer set forth to her team, the best and brightest asking for ways to obtain this information at runtime.

It was there, at this very team meeting that command line applications changed forever.

"Throughout all of our calculations, there appears to be only a handful of methods for getting information at runtime!" one developer proclaimed.

"From the environment!" Yelled one.

"Also from a file, or by asking!" Said another with far too much enthusiasm.

"Ney!" Said the lead developer, "Asking for the file, while seemingly simple, won't allow `wc` to be included in scripts! Setting an environmental variable for each invocation seems cumbersome. Especially with the lack of namespacing!"

"And adding information to a file, that must be created, read, and parsed is far too much leg work!" said the overly enthusiastic developer.

The lead developer was beginning to worry that perhaps there wasn't a solution, that perhaps `wc` was doomed to a life of re-complilation.

Then, a small voice in the back began to speak. At first, everyone thought it may have been a television left on in another room. But sure enough, the voice spoke louder, and a young developer stood up, "The answer is argument parsing."

"Yes, I've dreamed of such magic." Said the lead developer, "We will have users tell `wc` which file to parse while invoking `wc` itself!"

Developers large and small, young and old, gathered round to watch this small developer with a shy voice change the source ever so slightly to use this new sorcery. Once the compiler returned the successful binary, all gathered round to watch what had transpired.

```
$ wc test.txt
 50 78 549 test.txt
```

The heavens had heard no such joys before! The problem was solved, for now...
