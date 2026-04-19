#### Current State


Surprisingly, I managed to make the system libc replacement stable.

Main struggle had been heisenbugs, like small string copys,
which in turn are executed by the internal cpu optimizer out of order.

There's no dynamic loader, therefore the libc isn't suitable for linking 
with larger libraries, like gtk/Qt, and such.

On the other hand, I also do not see any advantage for the combination mlibc/gtk, 
mlibc is optimized for small size, what results in (sometimes surprising) 
latency and faster execution.

Both are things, unimportant in the context of large desktop libraries.




