GreenCoin integration/staging tree
================================

New Roadmap:
// Work to eliminate Main.cpp and move to modules - move fees to own file, coin controls, remove antiquated miner controls, etc.
// Specific Functions/Variables to move / roadmap
// nTransactionFee
// Mempool(Check Files for Mempool traces)
// Alerts (Move to Alerts?)
// Charity Address Function - Allow for Stakers to donate higher %'s of staked coins
// Merkle (Assign as set values? No need to clutter here)
// PoW Leftovers - Remove Traces of PoW left over from PoS that are no longer used.
// GreenCoinMiner - Remove PoW pieces (Leave chain design aspects for coin control)
// AmountCompression - Move to own module

// ADD TXN FEE CONTROL TO CLIENT.

http://www.grcoin.com

Copyright (c) 2009-2017 Bitcoin Developers
Copyright (c) 2011-2017 Litecoin Developers

What is GreenCoin?
----------------

GreenCoin is a Carbon Free Cryptocurrency utilizing a proof-of-stake (PoS) algorithm.
 - 63 second block targets
 - subsidy halves in 2.5 Million blocks (~5 years)
 - 10 Billion total coins
 - 2000 coins per block (50% to GreencoinFoundation, 50% to miners -> See main.cpp for changes, marked with //greencoin)
 - ~30 blocks to retarget difficulty

For more information, as well as an immediately useable, binary version of
the GreenCoin client sofware, see http://www.grcoin.com.

License
-------

GreenCoin is released under the terms of the MIT license. See `COPYING` for more
information or see http://opensource.org/licenses/MIT.

Development process
-------------------

Developers work in their own trees, then submit pull requests when they think
their feature or bug fix is ready.

If it is a simple/trivial/non-controversial change, then one of the GreenCoin
development team members simply pulls it.

If it is a *more complicated or potentially controversial* change, then the patch
submitter will be asked to start a discussion (if they haven't already) on the
[mailing list](http://sourceforge.net/mailarchive/forum.php?forum_name=bitcoin-development).

The patch will be accepted if there is broad consensus that it is a good thing.
Developers should expect to rework and resubmit patches if the code doesn't
match the project's coding conventions (see `doc/coding.txt`) or are
controversial.

The `master` branch is regularly built and tested, but is not guaranteed to be
completely stable. [Tags](https://github.com/bitcoin/bitcoin/tags) are created
regularly to indicate new official, stable release versions of GreenCoin.

Testing
-------

Testing and code review is the bottleneck for development; we get more pull
requests than we can review and test. Please be patient and help out, and
remember this is a security-critical project where any mistake might cost people
lots of money.

### Automated Testing

Developers are strongly encouraged to write unit tests for new code, and to
submit new unit tests for old code.

Unit tests for the core code are in `src/test/`. To compile and run them:

    cd src; make -f makefile.unix test

Unit tests for the GUI code are in `src/qt/test/`. To compile and run them:

    qmake BITCOIN_QT_TEST=1 -o Makefile.test bitcoin-qt.pro
    make -f Makefile.test
    ./GreenCoin-qt_test

