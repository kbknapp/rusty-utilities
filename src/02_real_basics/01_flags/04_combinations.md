# Combining Long and Short Forms

Attempt to prioritize common flags, or flags which you believe will be used the most. The prioritization I use is, from most use, to least use:

 * Both long and short form, short form has a shared lower-case character
 * Both long and short form, short form has a shared upper-case character
 * Both long and short form, short form has non-shared lower-case character
 * Both long and short form, short form has a non-shared upper-case character
 * Long form only
 * Short form only, lower-case character
 * Short form only, upper-case character

It's also a good practice to do a little forward thinking and try to reserve short forms for common flags you may not have implemented yet, but intend to. Adding a short form to a later version doesn't break backwards compatibility, but changing or removing a short form of a flag *does* break it, and can dampen ones reputation in the worst case.
