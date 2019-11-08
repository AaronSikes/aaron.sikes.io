---
layout: post
title: Some things I did at the Recurse Center
---

This summer I attended a 12-week self-directed programming retreat
at [the Recurse Center][rc] in NYC. Here are a few things I did.

Rust
----
I finished [the Rust book][book], implemented [some
lists][too-many-lists], and tried to implement a virtual machine for
a small, functional assembly format. It technically worked, but would
overflow the stack for anything non-trivial. I took a stab at making it
iterative instead of recursive, but it got a bit out of hand and I never
finished it.

TLA+ and formal methods
-----------------------
[TLA+][tla] is a formal modeling language and model checker. You specify
properties you want to always be true or eventually be true, and by
exhaustively checking every possibility it can give you a step-by-step
reproduction if those properties are violated. It is particularly
suited for concurrent algorithms and distributed systems, but it has
other uses as well. I implemented some well-known concurrent processes
like two-phase commit, and found the expected errors in some flawed
algorithms.

I feel more powerful now - I can be certain of some things that I could
only be pretty sure about before, and I think differently about systems.


Nix
---

[Nix][nixos] is a functional build tool and package manager, with an
associated Linux distribution and deployment tool. Rather than relying
on a globally installed libssl, or requiring your installed
version of node.js to be of a certain version, a package's build and runtime
dependencies are all specified explicitly.

In fact, it takes great pains
to help weed out uses of global state that you might not know about.
When running a build it creates a new empty build directory to do things
in. It clears the PATH, so only commands you bring in on purpose can be
used. It changes the HOME environment variable to a non-existant folder,
so that per-user configuration is hopefully not being used. You can even
configure it to run the build inside a `chroot` that has no access to
your normal filesystem!

All this adds up to very repeatable builds. If you've built something
once, you won't need to build it again unless it or its dependencies
change. And because it's so reliable, you don't even have to run most
builds - they can be run once by the community, and a cache of these
pre-compiled artifacts can simply be downloaded.

There's a functional package management system built on top of this
reliable substrate. Because everything is pure and there are no
interactions, you can manage these profiles of installed programs, and
easily switch or roll back changes you make. The system simply changes a
few symlinks!

And as long as you can manage these profiles functionally, why not use
it for your entire OS configuration! That's NixOS.



CRDTs, my wiki, and dreamy persistence
--------------------------------------

icalling card
data laced
offline
deepest learning, most of batch.
livepad prototype
demo wiki
offline-first storage
service workers



[rc]: https://recurse.com
[book]: https://doc.rust-lang.org/book/
[too-many-lists]: https://rust-unofficial.github.io/too-many-lists/
[tla]: https://en.wikipedia.org/wiki/TLA%2B
[nixos]: https://nixos.org/
