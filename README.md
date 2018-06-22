Sapotacoin integration/staging tree
================================

http://www.sapotacoin.org

Copyright (c) 2009-2014 Bitcoin Developers
Copyright (c) 2011-2014 Sapotacoin Developers

What is Sapotacoin?
----------------

Sapotacoin is a lite version of Bitcoin using scrypt as a proof-of-work algorithm.
 - 2.5 minute block targets
 - subsidy halves in 840k blocks (~4 years)
 - ~210 million total coins

The rest is the same as Bitcoin.
 - 125 coins per block
 - 2016 blocks to retarget difficulty

For more information, as well as an immediately useable, binary version of
the Sapotacoin client sofware, see http://www.sapotacoin.org.

License
-------

Sapotacoin is released under the terms of the MIT license. See `COPYING` for more
information or see http://opensource.org/licenses/MIT.

Development process
-------------------

Developers work in their own trees, then submit pull requests when they think
their feature or bug fix is ready.

If it is a simple/trivial/non-controversial change, then one of the Sapotacoin
development team members simply pulls it.

If it is a *more complicated or potentially controversial* change, then the patch
submitter will be asked to start a discussion with the devs and community.

The patch will be accepted if there is broad consensus that it is a good thing.
Developers should expect to rework and resubmit patches if the code doesn't
match the project's coding conventions (see `doc/coding.txt`) or are
controversial.

The `master` branch is regularly built and tested, but is not guaranteed to be
completely stable. [Tags](https://github.com/sapotacoin-project/sapotacoin/tags) are created
regularly to indicate new official, stable release versions of Sapotacoin.
Important Library Link 
-----------------------
https://github.com/litecoin-project/litecoin/blob/master/doc/build-unix.md

Installation Library
----------------------------
sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils python3
sudo apt-get install libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-program-options-dev libboost-test-dev libboost-thread-dev
sudo apt-get install libboost-all-dev
---------------------------------------
Optional (see --with-miniupnpc and --enable-upnp-default):
sudo apt-get install libminiupnpc-dev
---------------------------------------

ZMQ dependencies (provides ZMQ API 4.x):
sudo apt-get install libzmq3-dev
---------------------------------------
Dependencies for the GUI: Ubuntu & Debian
sudo apt-get install libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler
sudo apt-get install libqt4-dev libprotobuf-dev protobuf-compiler

libqrencode (optional) can be installed with:
sudo apt-get install libqrencode-dev

Run 
-------
 make -f makefile.unix USE_UPNP=-
 
GUI Wallet For Ubuntu
--------------------
 qmake "USE_QRCODE=1" "USE_UPNP=-" "USE_IPV6=1" sapotacoin-qt.pro

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

    qmake BITCOIN_QT_TEST=1 -o Makefile.test sapotacoin-qt.pro
    make -f Makefile.test
    ./sapotacoin-qt_test

