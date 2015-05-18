The stack uses a completely asynchronous design. All of open/read/write/close operations complete via a callback. [Boost.Asio](http://www.boost.org/doc/libs/1_43_0/doc/html/boost_asio.html) provides us with an asynchronous framework and cross-platform networking and serial support. This enables the execution of hundreds of parallel connections in a non-blocking manner with minimal thread overhead. Asio implements the [proactor pattern](http://www.boost.org/doc/libs/1_43_0/doc/html/boost_asio/overview/core/async.html). Almost more important than performance, thread-less code can be tested deterministically.

When implementing an asynchronous system, much of the program state that a synchronous implementation would carry implicitly on the call stack must now be carried explicitly in mutable data. Without discipline, this can lead to a rat's nest of mutable data. This library makes extensive use of the [state pattern](http://en.wikipedia.org/wiki/State_pattern) to mitigate this complexity. The other advantage of the state pattern is the software maps much more closely to the protocol specification. The newest versions of the dnp specification explicitly enumerate states and events. We have tried to map this as faithfully as possible were applicable.