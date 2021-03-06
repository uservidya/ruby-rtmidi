Ruby-RtMidi
===========

[![Build Status](https://travis-ci.org/adamjmurray/ruby-rtmidi.png)](http://travis-ci.org/adamjmurray/ruby-rtmidi)

[Ruby](http://www.ruby-lang.org/) wrapper for [RtMidi](http://www.music.mcgill.ca/~gary/rtmidi/index.html),
a cross-platform C++ library for realtime MIDI input and output.

Features:

* List MIDI I/O ports
* Send 3-byte MIDI messages to output ports
* Listen for 3-byte messages on input ports

In other words, it can handle [channel messages](http://www.cs.cf.ac.uk/Dave/Multimedia/node158.html)
(notes, control change, pitch bend, pressure, program),
but there is no support for [SySex](https://en.wikipedia.org/wiki/SysEx#System_Exclusive_messages) messages yet.

Supported Platforms:

* OS X
* Windows
* Linux with [JACK](http://jackaudio.org/) or [ALSA](http://www.alsa-project.org)


Requirements
============

To install, you need `gcc` and `g++` on your PATH.

On Windows, you can use Visual Studio's `cl.exe` compiler instead.

Here's the recommended approach for your system:

OS X Setup
----------

* Install XCode via the Apple AppStore.
* Open XCode's Preferences and install "Command Line Tools" in the Downloads tab.

See [this stackoverflow discussion](http://stackoverflow.com/questions/9329243/xcode-4-4-command-line-tools) for help.

Windows Setup
-------------

### with [Visual Studio](http://www.microsoft.com/visualstudio) (cl.exe)
* Install [Visual Studio](http://www.microsoft.com/visualstudio) (Tested with Visual C++ 2010 Express. Any recent version with a C++ compiler should work.)
* Use the "Visual Studio Command Prompt" to install

### with [MinGW](http://www.mingw.org/) (gcc/g++)
* [Install MinGW](http://sourceforge.net/projects/mingw/files/latest/download)
* During installation, on the "Select Components" screen, install the following:
  * C Compiler
  * C++ Compiler
  * MSYS Basic System
  * MinGW Developer ToolKit
* Use the the MinGW Shell (MSYS) to install

Note: when installing under MinGW, this library may not work outside of MinGW. If that is a problem for you, use Visual Studio to install.

Linux Setup (Ubuntu)
--------------------

    sudo apt-get install g++
    sudo apt-get install jackd
    sudo apt-get install libjack-dev


Installation
============

Assuming you have Ruby installed, and are ready to compile C++ code with `gcc`, this part is easy:

    gem install rtmidi


Usage
=====

See the following examples:

* [List MIDI devices](http://rdoc.info/github/adamjmurray/ruby-rtmidi/file/examples/list_ports.rb)
* [MIDI output](http://rdoc.info/github/adamjmurray/ruby-rtmidi/file/examples/play_notes.rb)
* [MIDI input](http://rdoc.info/github/adamjmurray/ruby-rtmidi/file/examples/monitor_input.rb)


Documentation
=============

[http://rdoc.info/github/adamjmurray/ruby-rtmidi/frames](http://rdoc.info/github/adamjmurray/ruby-rtmidi/frames)


Contributing
============

Pull requests are welcome. The following must work:

* `rake test` shows all unit tests are passing
* Build and test the gem manually:
    * `gem build rtmidi.gemspec`
    * `gem install rtmidi-#{version}.gem`
    * the examples can be run successfully against this version of the gem (`ruby examples/**`)


Changelog
=========

* 0.2.2 - Compilable with Visual Studio on Windows
* 0.2.1 - Linux support (thanks to [@quark-zju](https://github.com/quark-zju))
* 0.2 - First stable release
