# Java Decompiler
![Linux CI](https://github.com/Caellian/java-decompiler/workflows/Linux%20CI/badge.svg)
![MacOS CI](https://github.com/Caellian/java-decompiler/workflows/MacOS%20CI/badge.svg)
![Windows CI](https://github.com/Caellian/java-decompiler/workflows/Windows%20CI/badge.svg)
![Tests](https://github.com/Caellian/java-decompiler/workflows/Tests/badge.svg)

A modern and very efficient Java decompiler.

## State of the project

It's in early phases of development.
Environment is set up properly and ever commit is supposed to compile with both clang and gcc.
Currently, it reads class files properly, nothing is being done with that information however.

## JVM support status

Latest version is currently being written to support Java 14.
I'm planning on adding support for decompiling code to older versions later.
This is being kept in mind while I'm writing the initial working version as to reduce amount of rewrites later. 
I'd like to allow users to decompile code compiled by and compiler version for any specific JVM version, we'll see how
that goes...

## How fast is it?

Blazing fast. That being said, it doesn't actually do anything yet apart from reading class files and then disposing
of that memory. I'll compare it to fernflower when it's actually doing something. I'm also looking into the possibility
of adding multithreading support to make decompiling large JAR files a bit faster.

## Why C++20?

As of now, main reason is lack of alternatives to `std::endian` in earlier versions of the standard library.
I also like new C++20 features and I have a feeling some of them might help a lot when I start with instruction
handling.
I am planning on porting the decompiler to `C++11` later and that version will be kept in a separate branch in case
someone needs it.

An alternative for platforms where new compilers aren't available yet is to build them and possibly support the codebase
they rely on the most (the compiler).

## Why not just use fernflower?

Fernflower is amazing. I've read it's code several times.
It's written in Java though.
While I'm ok with Java (I love Kotlin) and think people are speaking nonsense when they say it's inefficient, it does
require more memory to run programs.
JVM also takes some time to warm up.
This is supposed to be an alternative for resource constricted environments.
It would also be great if it's faster by a large factor, but we'll see.
I expect some gain in speed which might be significant for large JARs.

## License

This project is licensed under the GPL license, version 3.
A copy of the GPL license is provided in the [LICENSE.md](LICENSE.md) file.

Files inside [.github](.github) directory are provided under MIT License.
A copy of the MIT license is provided in the [.github/LICENSE.md](.github/LICENSE.md) file.
