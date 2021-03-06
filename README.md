Post-quantum key exchange from the ring learning with errors problem
====================================================================

This software implements the key exchange protocol based on the ring learning with errors (ring-LWE) problem from the following paper:

* Joppe W. Bos, Craig Costello, Michael Naehrig, and Douglas Stebila. Post-quantum key exchange for the TLS protocol from the ring learning with errors problem. Cryptology ePrint Archive, Report 2014/599, August, 2014. <http://eprint.iacr.org/2014/599>

This software was initially distributed by the authors from <https://github.com/dstebila/rlwekex>

Instructions
------------
The software is plain C (C99 standard).  Compilation has been tested using gcc on Linux and clang on Mac OS X.  

To compile:

	make

To run the sample key generation program:

	./rlwe_main

To run the benchmark program:

	./rlwe_benchmark

Cryptographically secure random number generation
-------------------------------------------------
Note that the key generation and key exchange algorithms make use of a random number generator during execution.  The sampling code is configured by default to use OpenSSL's PRNG to generate a seed and expand it using AES.  Several other options are available; see `rlwe.c`.  C's `random()` can be used for testing purposes by defining the macro `RLWE_RANDOMNESS_USE_C_RANDOM_INSECURE`, but this is **not secure**.  Developers can also define the `RANDOM_VARS`, `RANDOM8`, `RANDOM32`, `RANDOM64` macros with a cryptographically secure pseudorandom number generator of their own choosing.  

License
-------
This is free and unencumbered software released into the public domain.

Anyone is free to copy, modify, publish, use, compile, sell, or distribute this software, either in source code form or as a compiled binary, for any purpose, commercial or non-commercial, and by any means.

See the file LICENSE for complete information.
