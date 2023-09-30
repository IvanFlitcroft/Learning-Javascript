# Understanding Typed Arrays

A typed array is a special kind of array-like object that is designed to efficiently store and manipulate binary data. Unlike regular JavaScript arrays, which can hold elements of various data types, typed arrays are restricted to holding elements of a single, specified data type.

## What are they used for?

They are mainly used for interacting with the low level binary data. This includes WebGL operations (API for rendering graphics so this could include altering rgb values), data from network sockets and things like that.

## What are the types of Typed Arrays

There are quite a few types of Typed Arrays mainly focused on the size of the integers and whether its Unsigned or signed.

The main frame of the typed arrays follows this `(?U)Int[8,16,32]Array'

There is a `Uint8ClampedArray` array which works with the image data as the 8 bit unsinged integers are clamped to values 0-255.
