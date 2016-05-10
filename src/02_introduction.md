# Introduction

Why write about building CLIs in Rust? Why use Rust to write a CLI? These are all questions one may be asking. And they're all great questions. Let me start with 'Why CLIs?' and then I'll move into the 'Why Rust?'

## Why Write about CLIs?

First and foremost, command line programs in general fascinate me. Granted, I hardly ever remember how to invoke their magic without some quick Googling or trial-and-error, but that's an aside. The fact that a single program could appear amazing simple and succinct, and then with a little digging be found to have such broad depth is amazing to me.

I also love the philosophy of combing small utilities for an even greater outcome. This can be difficult or impossible to do with Graphic User Interfaces (GUIs). Chaining operations between these various small utilities, all with a seemingly endless learning curve and near infinite possibilities makes my jaw drop.

Finally, my day job revolves around these little programs. Often times I can write a small utility to complete an otherwise mundane, or error prone task seamlessly. These little utilities can then often be placed into other scripts to combined in amazing ways.

This still doesn't answer why I'm writing about them. The answer is because there are some very (to me) important aspects that should be considered when designing a CLI, which is arguably the most, or one of the most critical pieces of your program. It's the part that users actually interact with. It's often the lasting feeling or memory about a particular program. A great program can be ruined by a poorly designed CLI, likewise a mediocre program may be utilized far more frequently simply because the interface is more appealing or well designed.

In this book I'm hoping to pass along a few of the idiosyncrasy I've learned while building and studying these interfaces. I'm not claiming to be an expert in either Rust or CLI design, rather far from it; I'm simply a man hoping to pass on a few tips and tricks to make building CLIs more enjoyable.

## Why Rust?

Although it's poor form to make assumptions, I will however assume that you're already at least mildly familiar with Rust and it's various benefits. But that also means you may be familiar with some of Rust's detractions as well. Some of these detractions may seem like they'd be directly at odds with aspects of building a command line application. Namely, things like lifetimes, and string manipulation are extremely common encounters while building command line utilities, yet strings in particular are arguably a little more difficult to work with in Rust, vice certain other languages.

After having built and dealt with multiple CLIs in Rust and various other languages I can unequivocally say that I prefer using Rust for building these applications. The benefits of Rust, it's speed, safety, ecosystem, and expressiveness far outweigh any detractions one might encounter while dealing with things like strings. Add to that, those problems with strings exist in other languages as well, they're just hidden from you until they pop out and ruin your lunch. Rust has the benefit of at least making their presence known, so that you can deal with it up front and center.

There are also various CLI libraries designed for Rust, that are in my opinion some of the best in any language. In fact, I miss their features sorely while building command line utilities in other languages.

Throughout this book I'll be demonstrating one of those libraries, [`clap`](clap). Full disclosure, I'm the primary developer behind clap, and it's the library that I'm most familiar with. I also believe it's one of the more powerful libraries in the Rust ecosystem for this purpose. Having said that, all principals demonstrated in this book can be implemented in other command line libraries as well. Two vary notable libraries that I'd highly recommend looking into if clap isn't to your liking are [`docopt`](docopt) and [`getopts`](getopts)

[clap]: https://github.com/kbknapp/clap-rs
[docopt]: https://github.com/docopt/docopt.rs
[getopts]: https://github.com/rust-lang-nursery/getopts
