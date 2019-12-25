# JavaFS [![Version](http://img.shields.io/badge/version-0.1.0-blue.svg?style=flat)](https://github.com/puniverse/javafs/releases)
## Java filesystems as FUSE

## Words about the "port"

I don't yet know whether I will ever attempt to actually cleanly get it running (since I don't yet know what that would require) similarly to its original form, so far this repo only contains the bare minimum to get it to compile. 

What I have done is roughly: 

- Remove Javadoc (or prevent it from running by adding ** as an excluded path)
- Remove tests (by commenting out the build step [or not?] and renaming the folder containing them)

I'm a complete noob in the Java ecosystem, so let's see, maybe I'll learn some things. 

## Requirements

JDK 13 seems to work. 

Your OS must support FUSE or have it installed.

## Building

`gradle build`. The output JARs will be in `build/libs/`. 

## Usage

The API consists of a single class with two methods: 

JavaFS.mount, which mounts a Java `FileSystem` as FUSE filesystem, and

JavaFS.unmount, which unmounts a FUSE filesystem

## Test

Removed. R.I.P.

#### Compatibility

* OS X with [MacFUSE]/[fuse4x]/[OSXFUSE] on Intel architectures
* Linux with [FUSE][Linux-Fuse] on Intel, PowerPC and ARM architectures
* FreeBSD with [FUSE][FreeBSD-Fuse] on Intel architectures

## Project Information

This is essentially a port of [fuse-jna], by Etienne Perot, from [JNA] to [JNR],
with some code copied from [jnr-fuse], by Sergey Tselovalnikov, made to work with the standard JDK [FileSystem] API.

* Differences from [fuse-jna]: this project uses [JNR] rather than [JNA].
* Differences from [jnr-fuse]: this project supports Java 7 (jnr-fuse supports only Java 8), and more platforms (like Mac).
* Differences from both: rather than exposing a new, specific, Java FUSE API, this project uses the standard [FileSystem] API.

## License

```
Copyright (c) 2015 Parallel Universe
Copyright (c) 2012-2015 Etienne Perot
Copyright (c) 2015 Sergey Tselovalnikov

Redistribution and use in source and binary forms, with or without modification, are
permitted provided that the following conditions are met:

   1. Redistributions of source code must retain the above copyright notice, this list of
      conditions and the following disclaimer.

   2. Redistributions in binary form must reproduce the above copyright notice, this list
      of conditions and the following disclaimer in the documentation and/or other materials
      provided with the distribution.

THIS SOFTWARE IS PROVIDED THE COPYRIGHT HOLDERS AND CONTRIBUTORS ''AS IS'' AND ANY EXPRESS OR IMPLIED
WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND
FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL <COPYRIGHT HOLDER> OR
CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR
CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON
ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING
NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF
ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```

This is the 2-clause BSD license.

[fuse-jna] is licensed under the [BSD 2-Clause License].

[jnr-fuse] is licensed under the [MIT License].


[fuse-jna]: https://github.com/EtiennePerot/fuse-jna
[jnr-fuse]: https://github.com/SerCeMan/jnr-fuse
[FileSystem]: http://docs.oracle.com/javase/7/docs/api/java/nio/file/FileSystems.html
[JNA]: https://github.com/java-native-access/jna
[JNR]: https://github.com/jnr
[MacFUSE]: http://code.google.com/p/macfuse/
[fuse4x]: http://fuse4x.org/
[OSXFUSE]: http://osxfuse.github.com/
[Linux-FUSE]: http://fuse.sourceforge.net/
[FreeBSD-FUSE]: http://wiki.freebsd.org/FuseFilesystem
[BSD 2-Clause License]: http://www.opensource.org/licenses/bsd-license
[MIT License]: http://opensource.org/licenses/MIT
