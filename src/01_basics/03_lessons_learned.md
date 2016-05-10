# Back to Reality

OK, so that was far too dramatic, and overly silly to be of much use. But we can learn from what's written above. Yes, for most programs to be of much use require a certain amount of information in order to operate correctly. Most often, this is information that can't be known at compile time.

Therefore the program must acquire said information at runtime in some manner, and like the overly enthusiastic developer above stated, there are only a handful of ways to do this. Each has their own strengths and weaknesses.

We will gloss over all but argument parsing, as the other methods are fairly straight forward and simple to use. It's argument parsing that can get very complex.

Keep in mind, that a good command line utility can absolutely take advantage of all methods for obtaining information, and isn't limited to simply once choice.
