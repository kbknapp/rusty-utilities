# About This Book

The purpose of this book is two-fold; first it's to explain how one could go about designing a Command Line Interface (or *CLI*), and second how to actually implement that design and build the program utilizing [Rust](rust).

Actually, it's three-fold; by teaching I learn. So there is actually a selfish aspect to this as well, by showing how to do something I also learn where the pain points are, and learn how well I understand, or rather don't, some of these concepts too. I also really enjoy teaching, so this is an outlet for those parts of my brain.

## Who this book is for

This book is designed for those interested in or who have a need to build command line applications or utilities. It is not specifically designed to be an introduction to Rust, although one may learn a thing or two along the way. If an introduction to Rust is needed, the [Rust Book](rust_book) is an excellent choice!

While this book goes into great detail about CLIs, starting from the basics, it generally assumes at least a basic knowledge of the Rust programming language. If one is comfortable with match expressions, modules, structs, enums, and basic Traits there should be very little difficulty along the way.

We may briefly speak about one of Rust's most notorious features; the dreaded lifetime, and how it can be applicable for and affect our command line programs. If you don't have a firm grasp on lifetimes, don't fear, the points we'll be discussing are quite low on the difficulty chart!

## Preface

Before we begin, let's ensure we're on the same page when it comes to some common terms.

### CLI (Command Line Interface)

I've used this term several times already, and it's destined to appear a few more. The term CLI is formally used to describe the portion of an application with which the user interacts from the command line or terminal. However, it is also often used refer to the program as a whole. This book attempts to be explicitly about whether it's speaking of the interface itself, or the program as a whole. If I mean the program as a whole, I will typically say things such as *program*, *application*, or *utility*.

### Command Line application

When speaking about command line applications, the defining feature is that they are invoked using a terminal emulator or shell prompt. Typically, all further interaction and output is also via the terminal output, files, or other non graphical display. This is not to say that command line applications can't have a graphical component, or that a graphical program can't be invoked or have a command line interface. Throughout this book we are referring to programs with whom all interaction is via the command line, regardless of where other interaction/output make take place in other usage modes.

## Requirements

In order to follow along with the examples in this book, or test one's own ideas, you will need a working Rust installation and an editor. That's it. I'd highly recommend using something like the still-beta-yet-amazing [`rustup.rs`](rustup) which allows one to have multiple Rust installations on a single computer and change between various versions of the compiler at will.

All examples in this book were tested using the current stable version of Rust, which as of this writing is `rustc 1.8.0 (db2939409 2016-04-11)`

[rust]: https://www.rust-lang.org/
[rust_book]: https://doc.rust-lang.org/book/
[rustup]: https://www.rustup.rs/
