leveldb
=======

Building a combined iOS and OSX library:

    make clean
    CXXFLAGS=-stdlib=libc++ make PLATFORM=IOS
    mv libleveldb.a libleveldb.a-ios
    make clean
    CXXFLAGS=-stdlib=libc++ make
    mv libleveldb.a libleveldb.a-osx
    lipo -create  libleveldb.a-ios libleveldb.a-osx -output libleveldb.a

Final result:

    Tue Dec 03 15:17:20 elcapitan:leveldb vikrum$ file libleveldb.a
    libleveldb.a: Mach-O universal binary with 6 architectures
    libleveldb.a (for architecture i386):	current ar archive random library
    libleveldb.a (for architecture armv6):	current ar archive random library
    libleveldb.a (for architecture armv7):	current ar archive random library
    libleveldb.a (for architecture armv7s):	current ar archive random library
    libleveldb.a (for architecture x86_64):	current ar archive random library
    libleveldb.a (for architecture cputype (16777228) cpusubtype (0)):	current ar archive random library
    
    Tue Dec 03 15:17:30 elcapitan:leveldb vikrum$


