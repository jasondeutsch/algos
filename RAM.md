When a computer is running code, it needs to keep track of *variables* (numbers, strings, arrays, etc.).

Variables are stored in **random access memory** (**RAM**). We sometimes call RAM "working memory" or just "memory.”

Think of RAM like a really tall bookcase with a *lot* of shelves. Like, *billions* of shelves.

The shelves are numbered.

We call a shelf's number its **address**.

Each shelf holds 8 **bits**. A *bit* is a tiny electrical switch that can be turned "on" or "off." But instead of calling it "on" or "off" we call it 1 or 0.

8 bits is called a **byte**. So each shelf has one byte (8 bits) of storage.

Of course, we also have a processor that does all the real work inside our computer:

It's connected to a **memory controller**. The memory controller does the actual reading and writing to and from RAM. It has a *direct connection* to each shelf of RAM.

That *direct connection* is important. It means we can access address 0 and then immediately access address 918,873 without having to "climb down" our massive bookshelf of RAM.

That's why we call it Random Access Memory (RAM)—we can *Access* the bits at any *Random*address in *Memory* right away.

Even though the memory controller can jump between far-apart memory addresses quickly, programs *tend to* access memory that's nearby. **So computers are tuned to get an extra speed boost when reading memory addresses that're close to each other**. Here's how it works:

The processor has a (series of ) **cache(s)** where it stores a copy of stuff it's recently read from RAM.

This cache is much faster to read from than RAM, so the processor saves time whenever it can read something from cache instead of going out to RAM.

**When the processor asks for the contents of a given memory address, the memory controller *also* sends the contents of a handful of *nearby* memory addresses. **And the processor puts *all* of it in the cache.

So if the processor asks for the contents of address 951, then 952, then 953, then 954...it'll go out to RAM once for that first read, and the subsequent reads will come straight from the super-fast cache.

But if the processor asks to read address 951, then address 362, then address 419...then the cache won't help, and it'll have to go all the way out to RAM for each read.

So reading from sequential memory addresses is faster than jumping around.