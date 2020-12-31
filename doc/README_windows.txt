REITIS integration/staging tree
================================

http://www.reitiscapital.com

Copyright (c) 2019 REITIS Developers

What is REITIS?
----------------
X15
PoS Minimum - 1 Day
PoS Maximum - Unlimited
PoS Interest - 12% Annually 
15 Blocks for REITISs to Mature
1 Minute Target Spacing
0 Coins Per POS stage/Block
5.500.000 Total Coins

P2P Port = 11019
RPC Port = 21020
Testnet Port = 31021

For more information, as well as an immediately useable, binary version of
the REITIS client sofware, see http://www.reitiscapital.com

Build Instructions for QT4 Linux Wallet
======================================
Create a folder named REITIS in /home/ and unpack the contents of ~/REITIS-master to that folder.

Install dependencies via Terminal:

$ sudo apt-get install build-essential libboost-all-dev libcurl4-openssl-dev libdb5.1-dev libdb5.1++-dev qt5-default qttools5-dev-tools qt-sdk make qrencode libqrencode-dev

//In terminal navigate to the REITIS folder.

$ cd /home/REITIS

//Enter into the terminal:

$ qmake -qt=qt4 "USE_QRCODE=1" "USE_UPNP=-"

//Then:

$ make

This will compile and build the QT Wallet which takes a little while, please be patient.

When finished you will have a file called REITIS-Core - Simply Double Click

//end of guide

Build Instructions for QT5 Linux Wallet
======================================
Create a folder named REITIS in /home/ and unpack the contents of ~/REITIS-master to that folder.

Install dependencies via Terminal:

$ sudo apt-get install build-essential libboost-all-dev libcurl4-openssl-dev libdb5.1-dev libdb5.1++-dev qt5-default qttools5-dev-tools qt-sdk make qrencode libqrencode-dev

//In terminal navigate to the REITIS folder.

$ cd /home/REITIS

//Enter into the terminal:

$ qmake -qt=qt5 "USE_QRCODE=1" "USE_UPNP=-"

//Then:

$ make

This will compile and build the QT Wallet which takes a little while, please be patient.

When finished you will have a file called REITIS-Core - Simply Double Click

//end of guide

Build Instructions for QT4 Linux Wallet
======================================
Create a folder named REITIS in /home/ and unpack the contents of ~/REITIS-master to that folder.

Install dependencies via Terminal:

$ sudo apt-get install build-essential libboost-all-dev libcurl4-openssl-dev libdb5.1-dev libdb5.1++-dev qt-sdk make qrencode libqrencode-dev

//In terminal navigate to the REITIS folder.

$ cd /home/REITIS

//Enter into the terminal:

$ qmake -qt=qt4 "USE_QRCODE=1" "USE_UPNP=-"

//Then:

$ make

This will compile and build the QT Wallet which takes a little while, please be patient.

When finished you will have a file called REITIS-Core - Simply Double Click

//end of guide


Build Instructions for Terminal Based Linux Wallet
===================================================
//Create a folder named REITIS in /home/ and unpack the contents of ~/REITIS-master to that folder.

//Install dependencies via Terminal:

$ sudo apt-get install build-essential libboost-all-dev libcurl4-openssl-dev libdb5.1-dev libdb5.1++-dev qt-sdk make 

//In terminal navigate to the REITIS folder.

$ cd /home/REITIS

//Enter into the terminal:

$ make -f makefile.unix "USE_UPNP=-"

//This will produce a file named REITISd which is the command line instance of REITIS-Core

//Now type:

$ strip REITISd

//When finished you will have a file called REITISd

//To run REITIS

$ ./REITISd & 

//It will complain about having no REITIS.conf file, we'll edit the one provided and move it into place

$ cd ..
$ nano REITIS.conf

//Edit the Username and Password fields to anything you choose (but remember them) then save the file

$ mv REITIS.conf /home/REITIS/src/
$ cd src/
$ ./REITISd &

//The server will start. Here are a few commands, google for more.

$ ./REITISd getinfo
$ ./REITISd getmininginfo
$ ./REITISd getnewaddresss

//end of guide


License
-------

REITIS is released under the terms of the MIT license. See `COPYING` for more
information or see http://opensource.org/licenses/MIT.

Development process
-------------------

Developers work in their own trees, then submit pull requests when they think
their feature or bug fix is ready.

If it is a simple/trivial/non-controversial change, then one of the REITIS
development team members simply pulls it.

The patch will be accepted if there is broad consensus that it is a good thing.
Developers should expect to rework and resubmit patches if the code doesn't
match the project's coding conventions (see `doc/coding.txt`) or are
controversial.

The `master` branch is regularly built and tested, but is not guaranteed to be
completely stable. [Tags](https://github.com/REITIS-project/REITIS) are created
regularly to indicate new official, stable release versions of REITIS.

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

    qmake REITIS_QT_TEST=1 -o Makefile.test REITIS-Core.pro
    make -f Makefile.test
    ./REITIS-Core_test





