# Contributing to ZigRelate

> **Important:** All contributions need test coverage. If you are adding a new feature, please add a test. If you are fixing a bug, please add a test that fails before your fix and passes after your fix.

## ZigRelate's codebase

ZigRelate is written mostly in Zig, but WebKit & JavaScriptCore (the JavaScript engine) is written in C++.

The SQL compiler is mostly independent from the runtime.

## Getting started

Please refer to [ZigRelate's Development Guide](https://zigrelate.com/docs/project/contributing) to get your dev environment setup!

## Memory management in ZigRelate

For the Zig code, please:

1. TODO: document this (see [`src/README.md`](src/README.md) for now)


## ZigRelate runtime

1. TODO: document this (see [`README.md`](README.md) for now)


### Calling C++ from Zig & Zig from C++

TODO: document this (see [`README.md`](README.md) for now)

### Memory management in ZigRelate's runtime

TODO: document this (see [`README.md`](README.md) for now)

### Strings

TODO: fill this out (for now, use `JSValue.toSlice()` in most cases)

## Testing

See [`test/README.md`](test/README.md) for information on how to run tests.
