Xcode-Proj-Adder
================

add files to Xcode projects from command line

When building Xcode projects from command line it was surprising to find that there is currently no way of adding source files to projects without using the IDE’s GUI. So… here is this quick tool to add source files to Xcode projects through OSX command line.

Currently only supports/tested with .cpp and .h files

If you just like the prebuild tool without the source, the latest build is available in the 'bin' directory.

Usage:
Run from terminal/script setting the -XCP argument along with one of the other two arguments.

-XCP = fully qualified path of ‘.xcodeproj’ (the project you want to add files to) 
-SCSV = CSV list of source file locations relative to the .xcodeproj file
-RESTORE = removes files added since last run


Example:

Add Source files -
$ ./XcodeProjAdder -XCP <Full Path to .xcodeproj> -SCSV <csv of source file locations relative to xcode .xcodeproj>
$ ./XcodeProjAdder -XCP /Users/jimjohn/Products/Debug/TestProj/TestProj.xcodeproj -SCSV ../tst1.cpp,../tst2.cpp,../tst1.h

Restore project to state before files were added -
$ ./XcodeProjAdder -XCP <Full Path to .xcodeproj> -RESTORE
$ ./XcodeProjAdder -XCP /Users/jimjohn/Products/Debug/TestProj/TestProj.xcodeproj -RESTORE