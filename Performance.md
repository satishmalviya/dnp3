Many SCADA products quote performance numbers in terms of points/sec without specifying how the tests are conducted. These tests could be easily inflated by adjusting the test conditions, types reported, etc. Our integration test configuration is as follows:

  * 100 master/slave pairs talking on the loopback of a single machine
  * Unsolicited messages with no delay/pack timer
  * Even mixture of binary, analog, and counter events

This test can be found in **`DNP3Test/TestAsyncIntegration.cpp`**

With this configuration, a quad core **laptop** running Windows 7 can push 3 million points per second!

The number of measurements "pushed" is calculated as follows:

**NUMBER\_POINTS\_CHANGES\_CYCLE\*NUM\_CYCLES\*NUM\_PAIRS\*2**

We multiply the point count since a frontend would only have to perform 1/2 of the computation.

With the overhead of DNP + TCP/IP + ethernet + latency this effectively makes the stack network bound!