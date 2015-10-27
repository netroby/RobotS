# RobotS

Robots is a pure rust actor system library, it is meant to be a close implementation of [akka](akka.io).

## Build it

This library currently (2015/10/27) needs to be build with a nightly version of rustc because it
uses the clippy compiler plugin.

If you remove the compiler plugin, you will still need a beta version of the compiler since it uses
weak pointers.

In order to have multiple versions of the rust compiler on your machine you can use
[multirust](https://github.com/brson/multirust).

## Usage

This library is still very much a work in progress but does work (even though I would not recommend
using it now as it will most likely have many breaking changes for a month or two (2015/10/27)).

In order to see a sample use you can take a look at the current `src/main.rs`.

The short version is that you need to create structs that implement the `Actor` trait.
You will also need to instantiate an `ActorSystem` (there is currently only one struct but it will be
moved to a trait to allow for different policies to be present).

Create your actors through the `ActorSystem` and simply implement their `handle` method to deal
with messages the way you desire.