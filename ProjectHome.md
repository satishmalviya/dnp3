## Goal ##

The goal of this project is to provide the utility industry with a production-ready reference implementation of [Distributed Network Protocol (DNP3)](http://www.dnp.org) under a commercially compatible license.

## Support ##

A [Google Group](http://groups.google.com/group/open-dnp3) is used for mail lists and archived discussion. Users requests and developer feedback can be posted to this list. Developers are friendly and quick to respond.

The project is part of the [Total Grid Community](http://www.totalgrid.org/) sponsored by [Green Energy Corp (GEC)](http://www.greenenergycorp.com). A commercially supported branch is offered by [Automatak](http://dnp3.github.com).

## Applications ##

The library is targeted for platforms with an operating system and a C++ compiler. It is primarily for high-performance SCADA server applications, but embeds nicely on linux based IEDs that cross compile to ARM. Primary applications include:

  * Frontends with scalability up to the OS socket limits
  * Highly parallel slave device simulations
  * Embedded linux based gateways, RTUs, and IEDs

It is **NOT** a traditional low-level C library. In our experience, these libraries are necessary for micro-controller IED implementations, but are less desirable for high-level DNP3 interoperability and performance in server applications.

## Features ##

  * Level 2+ master/slave library.
  * High-level API for creating user applications abstracts DNP3 specifics
  * Over 400 individual test cases providing [85-90% test coverage](https://ci.totalgrid.org/)
  * [Scalable performance](Performance.md) for front end processors and device simulations
  * 3rd party tool was used to remedy conformance issues
  * TCP/IP and serial support via [Boost.Asio](http://www.boost.org/doc/libs/1_47_0/doc/html/boost_asio.html)
  * Masters/slaves/ports can be added/removed dynamically at runtime
  * Multi-drop support (multiple devices per communication port)
  * Bindings for Microsoft CLR. Run the stack from any .NET language.
  * Automatically generated Java bindings. Use the library with JVM languages.
  * Platform-neutral C++ verified on 32/64 bit Windows, Linux, and embedded Linux ARM

## Topics ##

  * [Source Respository](https://github.com/gec/dnp3) on Github
  * [Instructions](Contribution.md) for becoming a contributor.
  * [Continuous Integration](ContinuousIntegration.md) - The CI server is [here](https://ci.totalgrid.org)
  * [Community wish list](CommunityWishList.md) - Desired features for future releases
  * [Performance testing](Performance.md) - The test cases and metrics used
  * [Design issues](Design.md) - Architecture and patterns
  * [Security](Security.md) - Security testing
