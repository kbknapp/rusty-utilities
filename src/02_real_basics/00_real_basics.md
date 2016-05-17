# The Basics

Before we start getting into the real code we need to first discuss some of the fundamental building blocks of argument parsing. Without these building blocks, we'll be running all willy-nilly like.

Imagine a carpenter was learning to build a house, but instead of being told how to use the tools of his trade, the senior carpenter just dumped a tool bag on the ground and said, "Go forth and build!" Sure, some houses would get built, but the new carpenter might just end up using a hammer to emplace screws, or a machete to cut the lumber.

In this chapter, I hope to give a little bit of direction about the fundamental tools of the argument parsing profession, so to speak. Luckily for us there aren't *that* many tools, in fact there's only four primary ones that we need to cover before we start really implementing these things.

The things we'll cover are:

 * Flags
 * Positional (or *free*) arguments
 * Options
 * Sub-commands
 * Requirements
 * Conflicts

 Of course, there are many more things to consider when building a CLI, but for now these are the four main tools of the trade. Interestingly, like the carpenter's tools, each of these may be able to do the job of some of the others to varying degrees of success. Here's is where I hope to teach you to drive nails with a hammer, and cut lumber with a saw.

 ## Disclaimer

Even if you're familiar with the above terms, I'd recommend at least skimming this chapter. Like the lonely carpenter above, you may not realize you're using a drill to dig a hole...or better yet, perhaps you'll notice and inform me where I'm using circular saw to mow the lawn. ;)
