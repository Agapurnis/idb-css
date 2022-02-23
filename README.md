# idb-css
A set of packages that allows for the seamless and persistant storage of complex classes with cyclic structures, and much more!

## How does it work?

Way too many proxies and property descriptors.

## Should I use it?

[Probably not.](https://github.com/Agapurnis/idb-css/wiki/Disclaimer)

## Tell me more.

As mentioned previously, the goal of this project is to allow the seamless and persistant storage of complex classes with cyclic structures.

By "complex classes", this is referring to classes with things like getter/setters, static properties, methods, and the usage of other decorators^[1].

The "seamless and persistant storage" means that as soon^[2] as a change is made, it is saved directly to the IndexedDB, and upon reload, you have the exact same state you did previously upon loading using the appropriate methods.

In the future, packages/plugins will be made for the following:
 - Historical difference traversal for the undoing/redoing of changes.
 - Importing/exporting portions or the entirety of the stored state.
 
^[1]: The usage of other decorators is currently not officially supported!
^[2]: There will always be some delay, but it is often negligable, and hooks are available for state synchronization events. This delay may also be impacted by the usage of the write-queueing functionality.

## How easy is it to use?

It's very easy to use once setup is completed, but there are a few drawbacks:
 - Setup is an asynchronous function that resolves with the decorators to be used. This can be inconvenient to setup.
 - Unexpected behavior could occur with the usage of other decorators.
 - Unexpected behavior could occur with the modification of prototypes or lower-level property mutations.
 - This library makes great use of Proxies, which have the potential to be slow, especially depending on the engine used.
 - This library creates properties on class instances, and 'hides' others. This can cause unexpected issues in deserialiation.

Note that some of this behavior may change in the future!

## I need the documentation.

Coming soon!

## When does it come out?

I'm not sure! Progress has been slow and steady, but most of the work has been done already.

The current goal is to ensure that there is adaquete testing of the library prior to any usage. After this has been done, things will be polished, and eventually synchronized and published.

If you would like to stay up-to-date, you can check out the status of features [here](https://github.com/Agapurnis/idb-css/projects/1)!
