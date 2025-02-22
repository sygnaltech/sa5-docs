# Element Tracking



## Map v. WeakMap

Both \`Map\` and \`WeakMap\` are built-in objects in JavaScript that can store key-value pairs, but there are some key differences between them:\


1\. \*\*Key Types\*\*: In a \`Map\`, keys can be of any type: primitives, objects, functions, etc. In a \`WeakMap\`, keys must be objects (not primitive values).

2\. \*\*Garbage Collection\*\*: One of the main differences between \`Map\` and \`WeakMap\` is how they interact with garbage collection. In a \`Map\`, as long as the \`Map\` itself is alive, all of its keys are kept alive too, even if there are no other references to those keys. This could potentially lead to memory leaks if you're not careful. On the other hand, in a \`WeakMap\`, if a key object is not referenced anywhere else, it can be garbage collected, and its entry is automatically removed from the \`WeakMap\`. This makes \`WeakMap\` useful for associating additional data with objects without affecting their lifetime.

3\. \*\*Enumeration\*\*: A \`Map\` is iterable, which means you can loop over its keys and values, and it has a \`size\` property that tells you how many entries it has. A \`WeakMap\` is not iterable and does not have a \`size\` property. This is mainly because of the way \`WeakMap\` interacts with garbage collection -- since keys can be automatically removed at any time, there's no guarantee of how many entries the \`WeakMap\` has at any moment.

4\. \*\*Use Cases\*\*: \`Map\` is a general-purpose key-value store that can be used in a wide variety of scenarios. \`WeakMap\` is more specialized. It's useful when you want to associate data with an object without interfering with garbage collection, such as storing metadata about objects, or keeping private data for an object.

So, in summary, while \`Map\` and \`WeakMap\` can both store key-value pairs, they have different characteristics regarding key types, garbage collection, enumeration, and use cases.



