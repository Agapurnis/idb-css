# idb-css
A set of packages that allows for the seamless and persistant storage of complex classes with cyclic structures, and much more!

## How does it work?

Way too many proxies and property descriptors.

## Should I use it?

[Probably not.](https://github.com/Agapurnis/idb-css/wiki/Disclaimer)

## Tell me more.

As mentioned previously, the goal of this project is to allow the seamless and persistant storage of complex classes with cyclic structures.

By "complex classes", I am referring to classes with things like getter/setters, static properties, methods, and usage of other decorators.

The "seamless and persistant storage" means that as soon^[1] as a change is made, it is saved directly to the IndexedDB, and upon reload, you have the exact same state you did previously upon loading using the appropriate methods.

In the future, packages/plugins will be made for the following:
 - Historical difference traversal for the undoing/redoing of changes.
 - Importing/exporting portions or the entirety of the stored state.

^[1]: There will always be some delay, but it is often negligable, and hooks are available for state synchronization events. This delay may also be impacted by the usage of the write-queueing functionality.

## How easy is it to use?

It's very easy to use once setup is completed, but there are a few drawbacks:
 - Setup is an asynchronous function whose output must be resolved and stored globally to be used.
 - Behavior might not work correctly if there are other heavy mutations being applied to a class.
 - It's not too fast, but in most cases it should work well-enough.
 - It might consume a considerable amount of memory.

Note that some of this behavior may change in the future!

### Configuration & Custom Builds

Due to the *'seamless'* part of the goal of this project, an effort is made to support a wide variety of environments.

You may not wish to support some of these environments in some cases. For example, by default (installing through a package manager), **you use a build with support for two/three different decorator specifications depending on the given configuration**. You almost certainly won't need that. To prevent the issue of distributing thousands of different builds for this repository, you must build the repository yourself with a certain configuration at buld-time, instead of providing it at runtime.

## I need the documentation.

Coming soon!

## When does it come out?

I'm not sure! Progress is being made slowly but steadily.

This library is currently being worked on in a private repository, and once I feel confident in the quality of the code, I'll sync it here.

If you would like to stay up-to-date, you can check out the status of features [here](https://github.com/Agapurnis/idb-css/projects/1)!
