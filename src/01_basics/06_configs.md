# Configuration Files

Next we reach configuration files, which aren't a bad choice in some instances. And are very common in certain settings. Similar to environmental variables, they should be used in circumstances where the information is fairly static. The downside to configuration files, is that it's typically a decent amount of work to load, and parse these files. Not to mention they must be present, and created in order to be used. Finally, if these files contain sensitive information, they must be protected in some manner.

Good examples of configuration file use can be found in things like [`rustfmt`](rustfmt) or [`clog`](clog) where it would be cumbersome to enter the information from those files at each invocation. Most of the information in those files also doesn't change between invocations.

[rustfmt]: https://github.com/rust-lang-nursery/rustfmt
[clog]: https://github.com/clog-tool/clog-cli
