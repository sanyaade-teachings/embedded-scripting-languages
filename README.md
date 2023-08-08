# Embedded scripting languages

The following is a list of reasonably mature open source [embedded scripting languages](https://en.wikipedia.org/wiki/Scripting_language) to use in your application.  Stretching the definition of a scripting language, it also includes [Datalog](https://en.wikipedia.org/wiki/Datalog) implementations.  Items with a strong copyleft license (like the GNU GPL) that will apply to the rest of your code are **highlighted** as a warning.

## Contents

- [Embedded scripting languages](#embedded-scripting-languages)
  * [Sorted by interpreted language](#sorted-by-interpreted-language)
  * [Sorted by implementation language](#sorted-by-implementation-language)
  * [See also](#see-also)
  * [Contributing](#contributing)
  * [License](#license)
  * [Disclosure](#disclosure)

## Sorted by interpreted language

| Language | Project name/link | Implementated in | GC | License | Notes |
|----------|-------------------|------------------|----|---------|-------|
| Ada | [HAC](https://hacadacompiler.sourceforge.io/) | Ada | None (stack only) | MIT | HAC implements a subset of the Ada language. Thus, it can share sources with the embedding application. |
| AngelScript | [AngelScript](http://www.angelcode.com/angelscript/) | C++ | Ref. counting + cycle-detecting tracing GC | zlib | A statically typed curly brace language resembling C++ itself. |
| Anko | [Anko](https://github.com/mattn/anko/) | Go | Go&#39;s GC | MIT | Scriptable interpreter with syntax similar to Go. |
| ArkScript | [ArkScript](https://github.com/SuperFola/Ark) | C++ | None (resource release is destruction + optional manual MM) | MPL 2.0 | A small functional Lisp-like programming language. Separate bytecode compiler and VM. |
| Awk | [Libmawk](http://repo.hu/projects/libmawk/) | C | Ref. counting | **GPL 2** | Implements Awk. A fork of mawk 1.3 restructured for embedding. |
| Awk, Basic, Pascal | [Libfawk](http://repo.hu/projects/libfawk/) | C | Ref. counting | 3-clause BSD | A multi-language VM. Includes compilers for three languages: Fawk (Awk dialect), Fbas (Basic dialect), and Fpas (Pascal dialect). |
| Basic | [MY-BASIC](https://github.com/paladin-t/my_basic) | C | Ref. counting + cycle-detecting tracing GC | MIT | A Basic dialect with prototype-based OOP. |
| Boron | [Boron](http://urlan.sourceforge.net/boron/) | C | Tracing | LGPL 3+ | An embeddable scripting language similar to Rebol. |
| C | [PicoC](https://github.com/zsaleeba/picoc) | C | None (manual MM) | 3-clause BSD | Statically typed. Interprets a subset of C. |
| C | [tcc](https://repo.or.cz/tinycc.git/) | C | None | LGPL 2 | A small C compiler that can be used as a library for a C JIT. [libtcc header](https://repo.or.cz/tinycc.git/blob/HEAD:/libtcc.h). [Embedding example](https://repo.or.cz/tinycc.git/blob/HEAD:/tests/libtcc_test.c). |
| C#, other CLR languages | [Mono](http://www.mono-project.com/docs/advanced/embedding/scripting/) | C | Tracing | MIT and other | Implements the [CLR](https://en.wikipedia.org/wiki/Common_Language_Runtime). |
| ChaiScript | [ChaiScript](http://chaiscript.com/) | C++ | Ref. counting | 3-clause BSD | A header-only C++14 interpreter library. |
| Clojure | [sci](https://github.com/borkdude/sci) | Clojure | host VM&#39;s GC | EPL | An interpreter for a subset of Clojure for Clojure and ClojureScript. |
| Common Lisp | [Clasp](https://github.com/drmeister/clasp) | Common Lisp, C++ | MPS GC (Boehm-Weiser also supported) | LGPL 2+ | Full Common Lisp implementation well integrated with C++, using LLVM for the code generation, to integrate closely with C++ applications or libraries. |
| Common Lisp | [Embeddable Common Lisp](https://gitlab.com/embeddable-common-lisp/ecl) | Common Lisp, C | Boehm-Weiser GC | LGPL 2+ | Full Common Lisp implementation, available as a shared library `libecl.so` embeddable in any C, C++ or other application. |
| daScript | [daScript](https://dascript.org/) | C++ | None (region-based + manual MM?) | 3-clause BSD | A statically-typed [performance-oriented](https://dascript.org/#performance) scripting language. |
| Datalog | [AbcDatalog](http://abcdatalog.seas.harvard.edu/) | Java | JVM&#39;s GC | 3-clause BSD | Implements Datalog. |
| Datalog | [Cascalog](https://github.com/nathanmarz/cascalog) | Clojure | JVM&#39;s GC | Apache License 2.0 | Implements Datalog. |
| Datalog | [Datalog (c-cube)](https://github.com/c-cube/datalog) | OCaml | OCaml&#39;s GC | 2-clause BSD | Implements Datalog. |
| Datalog | [Datalog (fogfish)](https://github.com/fogfish/datalog) | Erlang | None (no collection inside interpreter state) | Apache License 2.0 | Implements Datalog. |
| Datalog | [Datalog (MITRE Corporation)](http://datalog.sourceforge.net/) | C | Tracing (Lua&#39;s GC) | LGPL 2+ | Implements Datalog. It is implemented on top of Lua 5.3 and can be extended with Lua functions. |
| Dhall | [Dhall](https://dhall-lang.org/) | Haskell | Haskell&#39;s GC | 3-clause BSD | A statically-typed functional configuration language. Not Turing-complete. Untrusted code: can't access the file system, can fetch Dhall libraries over HTTP(S) from static URLs (but libraries aren't allowed to access your data), can use up memory and CPU time for a DoS attack. Has a work-in-progress Clojure and Ruby implementation. |
| Duktape | [Duktape](http://duktape.org/) | C | Ref. counting + cycle-detecting tracing GC | MIT | Implements JavaScript E5/E5.1. |
| DWScript | [DWScript](https://bitbucket.org/egrange/dwscript/) | Object Pascal (Delphi 2009 or later) | Ref. counting + cycle-detecting tracing GC | MPL 1.1, GPL 3 (JavaScript code generator) | [Description](https://www.delphitools.info/dwscript). A statically typed Delphi/Free Pascal-like language. Can compile to JavaScript. |
| Dyon | [Dyon](https://github.com/pistondevelopers/dyon) | Rust | None (Rust-style [lifetimes](http://www.piston.rs/dyon-tutorial/lifetimes.html)) | Apache License 2.0 or MIT | Has optional, optimistic (succeed-by-default) static type checking. |
| Expr | [Expr](https://github.com/antonmedv/expr) | Go | Go&#39;s GC | MIT | Compiles and evaluates statically-typed expressions. |
| Falcon | [Falcon](http://falconpl.org/) | C++ | Tracing | **GPL 2** or custom | The GC is pluggable. |
| Forth | [Atlast](https://www.fourmilab.ch/atlast/) | C | None (manual MM) | Public domain | A dialect of Forth originally developed at Autodesk. |
| Forth | [FTH](http://fth.sourceforge.net) | C | Tracing | 2-clause BSD | A dialect of Forth with objects, hashes, regular expressions, and other extensions. |
| Forth | [pForth](http://www.softsynth.com/pforth/) | C | None (manual MM) | Public domain | A dialect of Forth. |
| GameMonkey Script | [GameMonkey Script](http://www.gmscript.com/) | C++ | Tracing | MIT | Comes with C bindings. Similar to Lua, multithreaded. |
| Gentee | [Gentee](https://github.com/gentee/gentee/) | Go | Go&#39;s GC | MIT | Statically typed. |
| gluon | [gluon](https://github.com/gluon-lang/gluon) | Rust | Tracing | MIT | Statically typed. Inspired by Lua, Haskell, and OCaml. Each executing gluon thread gets a separate heap. |
| Gravity | [Gravity](https://github.com/marcobambini/gravity) | C | Tracing | MIT | A class-based concurrent scripting language with a Swift-like syntax. |
| Groovy | [Groovy](http://groovy-lang.org/) | Java | JVM&#39;s GC | Apache License 2.0 | A scripting language for the JVM. A large subset of Java is valid Groovy. [Integrating Groovy into applications](http://groovy-lang.org/integrating.html). |
| Haxe | [HashLink](https://hashlink.haxe.org/) | C | Tracing (lazy sweep) | MIT | A bytecode interpreter and a baseline JIT compiler (x86/x86\_64 only) for [Haxe](https://haxe.org/). |
| Haxe, others | [Neko](http://nekovm.org/) | C | Boehm | MIT | The NekoVM is a target for several compilers, including [Haxe](http://haxe.org/). |
| Io | [Io](https://github.com/stevedekorte/io) | C | Tracing | 3-clause BSD | A prototype-based OO language. |
| Janet | [Janet](https://janet-lang.org/) | C | Tracing | MIT | A functional and imperative language with a Lisp syntax. |
| Java | [BeanShell](https://github.com/beanshell/beanshell/) | Java | JVM&#39;s GC | Apache License 2.0 | An small, embeddable Java source code interpreter. Understands Java code with certain extensions like method closures. |
| JavaScript | [Espruino](https://github.com/espruino/Espruino) | C | Tracing | MPL 2.0 | Implements a subset of JavaScript ES5 in a way suitable for embedded hardware with 8+ KiB RAM. |
| JavaScript | [Goja](https://github.com/dop251/goja) | Go | Go&#39;s GC | MIT | Implements ECMAScript 5.1. Better standard compliance and performance than otto. |
| JavaScript | [JerryScript](https://github.com/jerryscript-project/jerryscript) | C | Tracing | Apache License 2.0 | A full ECMAScript 5.1 interpreter written in C99 and optimized for low memory consumption. Uses CMake. |
| JavaScript | [jsish](http://jsish.org/) | C | Ref. counting | MIT | A JavaScript ES 5.2+ interpreter. Internally structured after Tcl with an extensive C API. Features include subinterpreters, introspection, SQLite bindings, and a web framework with WebSocket support. The code is valid C and C++. |
| JavaScript | [MuJS](https://mujs.com/) | C | Tracing | ISC | Implements JavaScript (ES5). Has a similar C interface to Lua. |
| JavaScript | [njs](https://nginx.org/en/docs/njs/) | C | None (no collection performed) | 2-clause BSD | Implements a subset of ES5.1 with some ES6 extensions. |
| JavaScript | [otto](https://github.com/robertkrimen/otto) | Go | Go&#39;s GC | MIT | Implements ES5 with [some limitations](https://github.com/robertkrimen/otto#caveat-emptor). |
| JavaScript | [QuickJS](https://bellard.org/quickjs/) | C | Ref. counting + cycle-detecting tracing GC | MIT | A small embedded JavaScript interpreter that implements almost all of ES2019 and much of ES2020. |
| Jinx | [Jinx](https://jamesboer.github.io/Jinx/) | C++17 | Ref. counting | MIT | Designed for use in realtime applications such as video games. |
| Jsonnet | [Jsonnet](https://jsonnet.org/) | C++ | Tracing | Apache License 2.0 | A functional configuration language that extends JSON. Untrusted code: can't access the file system or network, can use up memory and CPU time for a DoS attack. Has [bindings](https://jsonnet.org/ref/bindings.html) for C, C++, Go, Python, and other languages, as well as a separate native Go implementation. |
| Ketos | [Ketos](https://github.com/murarth/ketos) | Rust | None (no heap allocation)? | Apache License 2.0 | A functional Lisp. |
| LIL | [LIL](http://runtimeterror.com/tech/lil/) | C, Object Pascal (separate implementations) | None (no reference support) | zlib | A Tcl-like language incompatible with mainline Tcl. |
| Lily | [Lily](https://github.com/FascinatedBox/lily/) | C | Ref. counting + GC | MIT | A language focusing on expressiveness and safety. |
| ljs | [ljs](https://github.com/mingodad/ljs) | C | Tracing | MIT | Lua 5.3, Lua 5.1, and LuaJIT with a C/C++/Java/JavaScript syntax. Can convert Lua source code to ljs. |
| Lua | [Go-Lua](https://github.com/Shopify/go-lua) | Go | Go&#39;s GC | MIT | Implements a subset of Lua 5.2. |
| Lua | [GopherLua](https://github.com/yuin/gopher-lua) | Go | Go&#39;s GC | MIT | Implements Lua 5.1 with the added support for Go's channels. Lacks the debug hooks and several functions from the C version. |
| Lua | [Lua](http://lua.org/) | C | Tracing | MIT | The reference implementation of what is likely the world's most popular embedded scripting language. Allows you to precompile scripts to bytecode. Versions 5.1-5.3, which are the ones used today, are not fully compatible with each other. |
| Lua | [LuaJ](https://sourceforge.net/projects/luaj/) | Java | JVM&#39;s GC | MIT | A Lua 5.2 spec-compliant interpreter written in Java for JME and JSE. Complies Lua directly to JVM bytecode. |
| Lua | [LuaJIT](http://luajit.org/) | C | Tracing | MIT | Fully compatible with Lua 5.1. Has a built-in C FFI library. [Performance comparison](https://luajit.org/performance.html). |
| Lua | [Lua-ML](https://github.com/lindig/lua-ml) | OCaml | OCaml&#39;s GC | 2-clause BSD | Embeddable Lua 2.5 reimplementation that integrates with OCaml type and module system. It's possible to extend or even replace the standard library with your own modules. |
| Lua | [Luau](https://luau-lang.org/) | C | Tracing | MIT | Roblox [fork of Lua 5.1](https://luau-lang.org/why) as a scripting language for games to support a gradual type system as well as limiting the set of standard libraries exposed to the users and implements extra sandboxing features to be able to run unprivileged code. Whenever possible, Luau aims to be backwards-compatible with Lua 5.1 and at the same time to incorporate features from later revisions of Lua. |
| Lua | [luerl](https://github.com/rvirding/luerl) | Erlang | Tracing | Apache License 2.0 | An implementation of Lua 5.2 in pure Erlang with some features like `goto` absent. |
| Lua | [MoonSharp](https://www.moonsharp.org/) | C# | CLR&#39;s GC | 3-clause BSD and other | CLR Based Lua implementation that is 99% compatible with Lua 5.2 |
| Mond | [Mond](https://github.com/Rohansi/Mond/) | C# | CLR&#39;s GC | MIT | A dynamically typed scripting language with generators, async, remote debugging, and a binding API. |
| Never | [Never](https://github.com/never-lang/never) | C | Tracing | MIT | A statically typed functional programming language. |
| Pascal | [Pascal Script](http://www.remobjects.com/ps.aspx) | Object Pascal | None (manual MM) | modified zlib/libpng-License with mandatory attribution | Statically typed. Implements "most of Object Pascal". Can't define new classes. |
| Pawn | [Pawn](http://www.compuphase.com/pawn/pawn.htm) | C | None (no heap allocation) | Apache License 2.0 with a clause to explicitly permit static linking | A curly-brace language with a small-footprint VM. Represents data as 4/8-byte "cells". Compiles to CPU-specific bytecode. [More](https://wiki.alliedmods.net/Pawn_Tutorial#Language_Paradigms). |
| Perl | [Perl](https://www.perl.org/) | C | Ref. counting | Artistic License or GPL 3 | [Embedding Perl in Another Application](https://perldoc.perl.org/perlembed) |
| PHP | [ephp](https://github.com/bragful/ephp) | Erlang | None (no collection inside interpreter state) | LGPL 2.1 | Implements a subset of PHP 5.5. |
| PHP | [PH7](https://github.com/symisc/PH7) | C | Ref. counting | **SPL** or proprietary | Implements a subset of PHP 5.3 with some changes like native UTF-8 support. |
| pocketlang | [pocketlang](https://github.com/ThakeeNathees/pocketlang) | C | Tracing | MIT | A small language syntactically similar to Ruby. [Embedding examples](https://github.com/ThakeeNathees/pocketlang/tree/master/tests/native/). [Performance comparison](https://github.com/ThakeeNathees/pocketlang#performance). |
| Prolog | [Erlog](https://github.com/rvirding/erlog) | Erlang | None () | Apache License 2.0 | Interprets a subset of standard Prolog. |
| Prolog | [Golog](https://github.com/mndrix/golog) | Go | Go&#39;s GC | MIT | Implements a subset of standard Prolog. |
| Python | [CircuitPython](https://github.com/adafruit/circuitpython) | C | Tracing | MIT | A fork of MicroPython, designed for API uniformity across many microcontrollers. |
| Python | [Jython](http://www.jython.org/) | Java | JVM&#39;s GC | PSFL (BSD-like) | An implementation of Python on the JVM. |
| Python | [MicroPython](https://github.com/micropython/micropython) | C | Tracing | MIT | Implements the Python 3.4 syntax and some of the core datatypes. |
| Python | [Python](https://www.python.org/) | C | Ref. counting + cycle-detecting tracing GC | PSFL (BSD-like) | [Embedding Python in Another Application](https://docs.python.org/3.5/extending/embedding.html). |
| QuakeC | [gmqcc/qcvm](https://github.com/graphitemaster/gmqcc) | C++ | None (no dynamic memory allocation) | MIT | A QuakeC compiler and VM. |
| Quirrel | [Quirrel](https://github.com/GaijinEntertainment/quirrel) | C++ | Ref. counting | MIT | A fork of Squirrel with [new features](https://quirrel.io/doc/reference/diff_from_original.html). |
| Rebol | [Rebol](https://github.com/Oldes/Rebol3) | C | Tracing | Apache License 2.0 | Relative Expression Based Object Language |
| Red | [Red](https://github.com/red/red) | Rebol, Red, Red/System | Tracing | 3-clause BSD, BSL | A descendant of Rebol. Embeddable via [libRed](https://github.com/red/docs/blob/master/en/libred.adoc). Features a cross-platform native GUI system. Intended to have low memory usage. |
| Rexx | [NetRexx](http://www.netrexx.org/) | Java | JVM&#39;s GC | ICU (BSD-like) |  |
| Rexx | [ooRexx](http://www.oorexx.org/) | C++ | Tracing | CPL | Implements Rexx extended with objects. |
| Rhai | [Rhai](https://github.com/jonathandturner/rhai) | Rust | None (Rust-style lifetimes) | MIT or Apache License 2.0 | An embedded scripting language for Rust inspired by ChaiScript. |
| Ring | [Ring](https://github.com/ring-lang/ring) | C | Tracing | MIT | An embeddable applications programming language with a large standard library and GIL-less multithreading. |
| Ruby | [JRuby](http://www.jruby.org/) | Java | JVM&#39;s GC | Choice of EPL, GPL, and LGPL | An implementation of Ruby on the JVM. |
| Ruby | [mruby](https://github.com/mruby/mruby) | C | Tracing | MIT | A lightweight implementation of Ruby. Has a compile-time package manager. |
| Ruby | [mruby/c](https://github.com/mrubyc/mrubyc) | C | Ref. counting | 3-clause BSD | An even smaller implementation of Ruby for microcontrollers with limited memory. |
| Ruby | [Ruby](https://www.ruby-lang.org/en/) | C | Tracing | Choice of 2-clause BSD, Ruby license, GPL 2 | An embeddable object-oriented scripting language. [Running Ruby in C](https://silverhammermba.github.io/emberb/embed/). |
| Scheme | [Animula](https://gitlab.com/hardenedlinux/animula) | C | Tracing | Compiler **GPL 3+** while VM is LGPL 3+ | An optimizing compiler and VM for embedded systems. R7RS. |
| Scheme | [Chibi Scheme](https://github.com/ashinn/chibi-scheme) | C | Tracing | 3-clause BSD | Implements R7RS small. |
| Scheme | [CHICKEN Scheme](https://call-cc.org/) | C | Tracing | 3-clause BSD | Implements R5RS (with some [changes](http://wiki.call-cc.org/man/4/Supported%20language)). R7RS support is a work in progress. [Examples of embedding CHICKEN](https://wiki.call-cc.org/embedding). |
| Scheme | [GNU Guile](https://www.gnu.org/software/guile/) | C | [Boehm](https://www.gnu.org/software/guile/manual/html_node/Conservative-GC.html) | LGPL 3+ | ["Guile mostly implements R6RS."](https://www.gnu.org/software/guile/manual/guile.html#R6RS-Support) |
| Scheme | [Kawa](https://www.gnu.org/software/kawa/) | Java | JVM&#39;s GC | MIT | R7RS. Supports the javax.script API. [Evaluating Scheme expressions from Java](https://www.gnu.org/software/kawa/Evaluating-Scheme-expressions-from-Java.html). |
| Scheme | [s7](https://ccrma.stanford.edu/software/snd/snd/s7.html) | C | Tracing | 3-clause BSD | Implements a subset of R5RS/R7RS. Descended from TinyScheme. |
| Scheme | [TinyScheme](http://tinyscheme.sourceforge.net/) | C | Tracing? | 3-clause BSD | Implements a subset of R5RS. |
| SGScript | [SGScript](https://github.com/snake5/sgscript) | C | Ref. counting + tracing CG | MIT | [Features](http://www.sgscript.org/pages/advdocs/sgscript.docs.htm#Why-SGScript) include a built-in data serialization format, coroutines, class-based OOP, sandboxed evaluation, a built-in debugger and profiler. |
| Shine | [Shine](https://github.com/richardhundt/shine) | C | Tracing | MIT | A language based on Lua with additional safety and expressiveness features implemented as a fork of LuaJIT. |
| SquiLu | [SquiLu](https://github.com/mingodad/squilu) | C++ | Ref. counting | MIT, some extensions LGPL or GPL | A fork of [Squirrel](http://squirrel-lang.org/). Changes the syntax to accept a subset of JavaScript and C/C++. Implements Lua's features like string pattern matching and global table manipulation functions. Adds extensions for database access (SQLite3, MySQL, PostgreSQL), sockets, and other features. |
| Squirrel | [Squirrel](http://squirrel-lang.org/) | C++ | Ref. counting | MIT | A language inspired by Lua and JavaScript/Python. Has a Lua-like C++ API. Differentiates itself from Lua with the use of reference counting in place of Lua's tracing GC, a curly-brace syntax, built-in class-based OOP, and zero-indexed arrays. |
| Starlark | [Starlark (Go)](https://github.com/google/starlark-go/) | Go | Go&#39;s GC | 3-clause BSD | A small dialect of Python for configuration. Not Turing-complete. Untrusted code: can't access the file system and network, can use up memory and CPU to perform a DoS attack. [Spec](https://github.com/bazelbuild/starlark). [Python bindings](https://github.com/caketop/python-starlark-go). |
| Starlark | [Starlark (Java)](https://github.com/bazelbuild/bazel/tree/master/src/main/java/net/starlark/java) | Java | JVM&#39;s GC | Apache License 2.0 | Starlark for the JVM. The original implementation. |
| Starlark | [Starlark (Rust)](https://github.com/google/starlark-rust/) | Rust | ? | Apache License 2.0 | Starlark in Rust. [Python bindings](https://github.com/inducer/starlark-pyo3). |
| Tcl | [Jim Tcl](http://jim.tcl-lang.org/) | C | Tracing | 2-clause BSD | Largely compatible with Tcl 8.5 with its own additions. |
| Tcl | [JTcl](https://github.com/jtcl-project/jtcl) | Java | Ref. counting | Various BSD-like | Tcl 8.4 with some 8.5 features for the JVM. |
| Tcl | [Molt](https://github.com/wduquette/molt) | Rust | Ref. counting | 3-clause BSD | A minimal Tcl implementation for Rust applications and libraries. |
| Tcl | [Picol](https://chiselapp.com/user/dbohdan/repository/picol/) | C | None (no reference support) | 2-clause BSD | A header-only library interpreter for a limited dialect of Tcl. |
| Tcl | [Tcl](http://tcl-lang.org/) | C | Ref. counting | Tcl license (BSD-like) | An embeddable general-purpose scripting language with a rich C API. Has a cross-platform GUI toolkit called [Tk](https://wiki.tcl-lang.org/477). [How to embed Tcl in C applications](https://wiki.tcl-lang.org/2074). |
| Umka | [Umka](https://github.com/vtereshkov/umka-lang) | C | Ref. counting | 2-clause BSD | Statically typed. |
| Wirefilter | [Wirefilter](https://github.com/cloudflare/wirefilter) | Rust | None (no dynamic memory allocation) | MIT | An expression language for Wireshark-like filters. |
| Wren | [Wren](https://github.com/munificent/wren) | C | Tracing | MIT | A small class-based performance-oriented scripting language. [Performance comparison](https://wren.io/performance.html). |
| zygomys | [zygomys](https://github.com/glycerine/zygomys) | Go | Go&#39;s GC | 2-clause BSD | An embedded Lisp for Go. Inspired by Clojure, but more oriented towards imperative programming. Has an infix syntax layer that looks like a subset of Go. |

## Sorted by implementation language

| Implementated in | Project name/link | Language | GC | License | Notes |
|------------------|-------------------|----------|----|---------|-------|
| Ada | [HAC](https://hacadacompiler.sourceforge.io/) | Ada | None (stack only) | MIT | HAC implements a subset of the Ada language. Thus, it can share sources with the embedding application. |
| C | [Animula](https://gitlab.com/hardenedlinux/animula) | Scheme | Tracing | Compiler **GPL 3+** while VM is LGPL 3+ | An optimizing compiler and VM for embedded systems. R7RS. |
| C | [Atlast](https://www.fourmilab.ch/atlast/) | Forth | None (manual MM) | Public domain | A dialect of Forth originally developed at Autodesk. |
| C | [Boron](http://urlan.sourceforge.net/boron/) | Boron | Tracing | LGPL 3+ | An embeddable scripting language similar to Rebol. |
| C | [CircuitPython](https://github.com/adafruit/circuitpython) | Python | Tracing | MIT | A fork of MicroPython, designed for API uniformity across many microcontrollers. |
| C | [Chibi Scheme](https://github.com/ashinn/chibi-scheme) | Scheme | Tracing | 3-clause BSD | Implements R7RS small. |
| C | [CHICKEN Scheme](https://call-cc.org/) | Scheme | Tracing | 3-clause BSD | Implements R5RS (with some [changes](http://wiki.call-cc.org/man/4/Supported%20language)). R7RS support is a work in progress. [Examples of embedding CHICKEN](https://wiki.call-cc.org/embedding). |
| C | [Datalog (MITRE Corporation)](http://datalog.sourceforge.net/) | Datalog | Tracing (Lua&#39;s GC) | LGPL 2+ | Implements Datalog. It is implemented on top of Lua 5.3 and can be extended with Lua functions. |
| C | [Duktape](http://duktape.org/) | Duktape | Ref. counting + cycle-detecting tracing GC | MIT | Implements JavaScript E5/E5.1. |
| C | [Espruino](https://github.com/espruino/Espruino) | JavaScript | Tracing | MPL 2.0 | Implements a subset of JavaScript ES5 in a way suitable for embedded hardware with 8+ KiB RAM. |
| C | [FTH](http://fth.sourceforge.net) | Forth | Tracing | 2-clause BSD | A dialect of Forth with objects, hashes, regular expressions, and other extensions. |
| C | [Gravity](https://github.com/marcobambini/gravity) | Gravity | Tracing | MIT | A class-based concurrent scripting language with a Swift-like syntax. |
| C | [GNU Guile](https://www.gnu.org/software/guile/) | Scheme | [Boehm](https://www.gnu.org/software/guile/manual/html_node/Conservative-GC.html) | LGPL 3+ | ["Guile mostly implements R6RS."](https://www.gnu.org/software/guile/manual/guile.html#R6RS-Support) |
| C | [HashLink](https://hashlink.haxe.org/) | Haxe | Tracing (lazy sweep) | MIT | A bytecode interpreter and a baseline JIT compiler (x86/x86\_64 only) for [Haxe](https://haxe.org/). |
| C | [Io](https://github.com/stevedekorte/io) | Io | Tracing | 3-clause BSD | A prototype-based OO language. |
| C | [Janet](https://janet-lang.org/) | Janet | Tracing | MIT | A functional and imperative language with a Lisp syntax. |
| C | [JerryScript](https://github.com/jerryscript-project/jerryscript) | JavaScript | Tracing | Apache License 2.0 | A full ECMAScript 5.1 interpreter written in C99 and optimized for low memory consumption. Uses CMake. |
| C | [Jim Tcl](http://jim.tcl-lang.org/) | Tcl | Tracing | 2-clause BSD | Largely compatible with Tcl 8.5 with its own additions. |
| C | [jsish](http://jsish.org/) | JavaScript | Ref. counting | MIT | A JavaScript ES 5.2+ interpreter. Internally structured after Tcl with an extensive C API. Features include subinterpreters, introspection, SQLite bindings, and a web framework with WebSocket support. The code is valid C and C++. |
| C | [Libfawk](http://repo.hu/projects/libfawk/) | Awk, Basic, Pascal | Ref. counting | 3-clause BSD | A multi-language VM. Includes compilers for three languages: Fawk (Awk dialect), Fbas (Basic dialect), and Fpas (Pascal dialect). |
| C | [Libmawk](http://repo.hu/projects/libmawk/) | Awk | Ref. counting | **GPL 2** | Implements Awk. A fork of mawk 1.3 restructured for embedding. |
| C | [Lily](https://github.com/FascinatedBox/lily/) | Lily | Ref. counting + GC | MIT | A language focusing on expressiveness and safety. |
| C | [ljs](https://github.com/mingodad/ljs) | ljs | Tracing | MIT | Lua 5.3, Lua 5.1, and LuaJIT with a C/C++/Java/JavaScript syntax. Can convert Lua source code to ljs. |
| C | [Lua](http://lua.org/) | Lua | Tracing | MIT | The reference implementation of what is likely the world's most popular embedded scripting language. Allows you to precompile scripts to bytecode. Versions 5.1-5.3, which are the ones used today, are not fully compatible with each other. |
| C | [LuaJIT](http://luajit.org/) | Lua | Tracing | MIT | Fully compatible with Lua 5.1. Has a built-in C FFI library. [Performance comparison](https://luajit.org/performance.html). |
| C | [Luau](https://luau-lang.org/) | Lua | Tracing | MIT | Roblox [fork of Lua 5.1](https://luau-lang.org/why) as a scripting language for games to support a gradual type system as well as limiting the set of standard libraries exposed to the users and implements extra sandboxing features to be able to run unprivileged code. Whenever possible, Luau aims to be backwards-compatible with Lua 5.1 and at the same time to incorporate features from later revisions of Lua. |
| C | [MicroPython](https://github.com/micropython/micropython) | Python | Tracing | MIT | Implements the Python 3.4 syntax and some of the core datatypes. |
| C | [Mono](http://www.mono-project.com/docs/advanced/embedding/scripting/) | C#, other CLR languages | Tracing | MIT and other | Implements the [CLR](https://en.wikipedia.org/wiki/Common_Language_Runtime). |
| C | [mruby](https://github.com/mruby/mruby) | Ruby | Tracing | MIT | A lightweight implementation of Ruby. Has a compile-time package manager. |
| C | [mruby/c](https://github.com/mrubyc/mrubyc) | Ruby | Ref. counting | 3-clause BSD | An even smaller implementation of Ruby for microcontrollers with limited memory. |
| C | [MuJS](https://mujs.com/) | JavaScript | Tracing | ISC | Implements JavaScript (ES5). Has a similar C interface to Lua. |
| C | [MY-BASIC](https://github.com/paladin-t/my_basic) | Basic | Ref. counting + cycle-detecting tracing GC | MIT | A Basic dialect with prototype-based OOP. |
| C | [Neko](http://nekovm.org/) | Haxe, others | Boehm | MIT | The NekoVM is a target for several compilers, including [Haxe](http://haxe.org/). |
| C | [Never](https://github.com/never-lang/never) | Never | Tracing | MIT | A statically typed functional programming language. |
| C | [njs](https://nginx.org/en/docs/njs/) | JavaScript | None (no collection performed) | 2-clause BSD | Implements a subset of ES5.1 with some ES6 extensions. |
| C | [Pawn](http://www.compuphase.com/pawn/pawn.htm) | Pawn | None (no heap allocation) | Apache License 2.0 with a clause to explicitly permit static linking | A curly-brace language with a small-footprint VM. Represents data as 4/8-byte "cells". Compiles to CPU-specific bytecode. [More](https://wiki.alliedmods.net/Pawn_Tutorial#Language_Paradigms). |
| C | [Perl](https://www.perl.org/) | Perl | Ref. counting | Artistic License or GPL 3 | [Embedding Perl in Another Application](https://perldoc.perl.org/perlembed) |
| C | [pForth](http://www.softsynth.com/pforth/) | Forth | None (manual MM) | Public domain | A dialect of Forth. |
| C | [PH7](https://github.com/symisc/PH7) | PHP | Ref. counting | **SPL** or proprietary | Implements a subset of PHP 5.3 with some changes like native UTF-8 support. |
| C | [PicoC](https://github.com/zsaleeba/picoc) | C | None (manual MM) | 3-clause BSD | Statically typed. Interprets a subset of C. |
| C | [Picol](https://chiselapp.com/user/dbohdan/repository/picol/) | Tcl | None (no reference support) | 2-clause BSD | A header-only library interpreter for a limited dialect of Tcl. |
| C | [pocketlang](https://github.com/ThakeeNathees/pocketlang) | pocketlang | Tracing | MIT | A small language syntactically similar to Ruby. [Embedding examples](https://github.com/ThakeeNathees/pocketlang/tree/master/tests/native/). [Performance comparison](https://github.com/ThakeeNathees/pocketlang#performance). |
| C | [Python](https://www.python.org/) | Python | Ref. counting + cycle-detecting tracing GC | PSFL (BSD-like) | [Embedding Python in Another Application](https://docs.python.org/3.5/extending/embedding.html). |
| C | [QuickJS](https://bellard.org/quickjs/) | JavaScript | Ref. counting + cycle-detecting tracing GC | MIT | A small embedded JavaScript interpreter that implements almost all of ES2019 and much of ES2020. |
| C | [Rebol](https://github.com/Oldes/Rebol3) | Rebol | Tracing | Apache License 2.0 | Relative Expression Based Object Language |
| C | [Ring](https://github.com/ring-lang/ring) | Ring | Tracing | MIT | An embeddable applications programming language with a large standard library and GIL-less multithreading. |
| C | [Ruby](https://www.ruby-lang.org/en/) | Ruby | Tracing | Choice of 2-clause BSD, Ruby license, GPL 2 | An embeddable object-oriented scripting language. [Running Ruby in C](https://silverhammermba.github.io/emberb/embed/). |
| C | [s7](https://ccrma.stanford.edu/software/snd/snd/s7.html) | Scheme | Tracing | 3-clause BSD | Implements a subset of R5RS/R7RS. Descended from TinyScheme. |
| C | [SGScript](https://github.com/snake5/sgscript) | SGScript | Ref. counting + tracing CG | MIT | [Features](http://www.sgscript.org/pages/advdocs/sgscript.docs.htm#Why-SGScript) include a built-in data serialization format, coroutines, class-based OOP, sandboxed evaluation, a built-in debugger and profiler. |
| C | [Shine](https://github.com/richardhundt/shine) | Shine | Tracing | MIT | A language based on Lua with additional safety and expressiveness features implemented as a fork of LuaJIT. |
| C | [Tcl](http://tcl-lang.org/) | Tcl | Ref. counting | Tcl license (BSD-like) | An embeddable general-purpose scripting language with a rich C API. Has a cross-platform GUI toolkit called [Tk](https://wiki.tcl-lang.org/477). [How to embed Tcl in C applications](https://wiki.tcl-lang.org/2074). |
| C | [tcc](https://repo.or.cz/tinycc.git/) | C | None | LGPL 2 | A small C compiler that can be used as a library for a C JIT. [libtcc header](https://repo.or.cz/tinycc.git/blob/HEAD:/libtcc.h). [Embedding example](https://repo.or.cz/tinycc.git/blob/HEAD:/tests/libtcc_test.c). |
| C | [TinyScheme](http://tinyscheme.sourceforge.net/) | Scheme | Tracing? | 3-clause BSD | Implements a subset of R5RS. |
| C | [Umka](https://github.com/vtereshkov/umka-lang) | Umka | Ref. counting | 2-clause BSD | Statically typed. |
| C | [Wren](https://github.com/munificent/wren) | Wren | Tracing | MIT | A small class-based performance-oriented scripting language. [Performance comparison](https://wren.io/performance.html). |
| C# | [Mond](https://github.com/Rohansi/Mond/) | Mond | CLR&#39;s GC | MIT | A dynamically typed scripting language with generators, async, remote debugging, and a binding API. |
| C# | [MoonSharp](https://www.moonsharp.org/) | Lua | CLR&#39;s GC | 3-clause BSD and other | CLR Based Lua implementation that is 99% compatible with Lua 5.2 |
| C++ | [AngelScript](http://www.angelcode.com/angelscript/) | AngelScript | Ref. counting + cycle-detecting tracing GC | zlib | A statically typed curly brace language resembling C++ itself. |
| C++ | [ArkScript](https://github.com/SuperFola/Ark) | ArkScript | None (resource release is destruction + optional manual MM) | MPL 2.0 | A small functional Lisp-like programming language. Separate bytecode compiler and VM. |
| C++ | [ChaiScript](http://chaiscript.com/) | ChaiScript | Ref. counting | 3-clause BSD | A header-only C++14 interpreter library. |
| C++ | [daScript](https://dascript.org/) | daScript | None (region-based + manual MM?) | 3-clause BSD | A statically-typed [performance-oriented](https://dascript.org/#performance) scripting language. |
| C++ | [Falcon](http://falconpl.org/) | Falcon | Tracing | **GPL 2** or custom | The GC is pluggable. |
| C++ | [GameMonkey Script](http://www.gmscript.com/) | GameMonkey Script | Tracing | MIT | Comes with C bindings. Similar to Lua, multithreaded. |
| C++ | [Jsonnet](https://jsonnet.org/) | Jsonnet | Tracing | Apache License 2.0 | A functional configuration language that extends JSON. Untrusted code: can't access the file system or network, can use up memory and CPU time for a DoS attack. Has [bindings](https://jsonnet.org/ref/bindings.html) for C, C++, Go, Python, and other languages, as well as a separate native Go implementation. |
| C++ | [ooRexx](http://www.oorexx.org/) | Rexx | Tracing | CPL | Implements Rexx extended with objects. |
| C++ | [gmqcc/qcvm](https://github.com/graphitemaster/gmqcc) | QuakeC | None (no dynamic memory allocation) | MIT | A QuakeC compiler and VM. |
| C++ | [Quirrel](https://github.com/GaijinEntertainment/quirrel) | Quirrel | Ref. counting | MIT | A fork of Squirrel with [new features](https://quirrel.io/doc/reference/diff_from_original.html). |
| C++ | [SquiLu](https://github.com/mingodad/squilu) | SquiLu | Ref. counting | MIT, some extensions LGPL or GPL | A fork of [Squirrel](http://squirrel-lang.org/). Changes the syntax to accept a subset of JavaScript and C/C++. Implements Lua's features like string pattern matching and global table manipulation functions. Adds extensions for database access (SQLite3, MySQL, PostgreSQL), sockets, and other features. |
| C++ | [Squirrel](http://squirrel-lang.org/) | Squirrel | Ref. counting | MIT | A language inspired by Lua and JavaScript/Python. Has a Lua-like C++ API. Differentiates itself from Lua with the use of reference counting in place of Lua's tracing GC, a curly-brace syntax, built-in class-based OOP, and zero-indexed arrays. |
| C++17 | [Jinx](https://jamesboer.github.io/Jinx/) | Jinx | Ref. counting | MIT | Designed for use in realtime applications such as video games. |
| C, Object Pascal (separate implementations) | [LIL](http://runtimeterror.com/tech/lil/) | LIL | None (no reference support) | zlib | A Tcl-like language incompatible with mainline Tcl. |
| Clojure | [Cascalog](https://github.com/nathanmarz/cascalog) | Datalog | JVM&#39;s GC | Apache License 2.0 | Implements Datalog. |
| Clojure | [sci](https://github.com/borkdude/sci) | Clojure | host VM&#39;s GC | EPL | An interpreter for a subset of Clojure for Clojure and ClojureScript. |
| Common Lisp, C | [Embeddable Common Lisp](https://gitlab.com/embeddable-common-lisp/ecl) | Common Lisp | Boehm-Weiser GC | LGPL 2+ | Full Common Lisp implementation, available as a shared library `libecl.so` embeddable in any C, C++ or other application. |
| Common Lisp, C++ | [Clasp](https://github.com/drmeister/clasp) | Common Lisp | MPS GC (Boehm-Weiser also supported) | LGPL 2+ | Full Common Lisp implementation well integrated with C++, using LLVM for the code generation, to integrate closely with C++ applications or libraries. |
| Erlang | [Datalog (fogfish)](https://github.com/fogfish/datalog) | Datalog | None (no collection inside interpreter state) | Apache License 2.0 | Implements Datalog. |
| Erlang | [ephp](https://github.com/bragful/ephp) | PHP | None (no collection inside interpreter state) | LGPL 2.1 | Implements a subset of PHP 5.5. |
| Erlang | [Erlog](https://github.com/rvirding/erlog) | Prolog | None () | Apache License 2.0 | Interprets a subset of standard Prolog. |
| Erlang | [luerl](https://github.com/rvirding/luerl) | Lua | Tracing | Apache License 2.0 | An implementation of Lua 5.2 in pure Erlang with some features like `goto` absent. |
| Go | [Anko](https://github.com/mattn/anko/) | Anko | Go&#39;s GC | MIT | Scriptable interpreter with syntax similar to Go. |
| Go | [Expr](https://github.com/antonmedv/expr) | Expr | Go&#39;s GC | MIT | Compiles and evaluates statically-typed expressions. |
| Go | [Gentee](https://github.com/gentee/gentee/) | Gentee | Go&#39;s GC | MIT | Statically typed. |
| Go | [Goja](https://github.com/dop251/goja) | JavaScript | Go&#39;s GC | MIT | Implements ECMAScript 5.1. Better standard compliance and performance than otto. |
| Go | [Golog](https://github.com/mndrix/golog) | Prolog | Go&#39;s GC | MIT | Implements a subset of standard Prolog. |
| Go | [Go-Lua](https://github.com/Shopify/go-lua) | Lua | Go&#39;s GC | MIT | Implements a subset of Lua 5.2. |
| Go | [GopherLua](https://github.com/yuin/gopher-lua) | Lua | Go&#39;s GC | MIT | Implements Lua 5.1 with the added support for Go's channels. Lacks the debug hooks and several functions from the C version. |
| Go | [otto](https://github.com/robertkrimen/otto) | JavaScript | Go&#39;s GC | MIT | Implements ES5 with [some limitations](https://github.com/robertkrimen/otto#caveat-emptor). |
| Go | [Starlark (Go)](https://github.com/google/starlark-go/) | Starlark | Go&#39;s GC | 3-clause BSD | A small dialect of Python for configuration. Not Turing-complete. Untrusted code: can't access the file system and network, can use up memory and CPU to perform a DoS attack. [Spec](https://github.com/bazelbuild/starlark). [Python bindings](https://github.com/caketop/python-starlark-go). |
| Go | [zygomys](https://github.com/glycerine/zygomys) | zygomys | Go&#39;s GC | 2-clause BSD | An embedded Lisp for Go. Inspired by Clojure, but more oriented towards imperative programming. Has an infix syntax layer that looks like a subset of Go. |
| Haskell | [Dhall](https://dhall-lang.org/) | Dhall | Haskell&#39;s GC | 3-clause BSD | A statically-typed functional configuration language. Not Turing-complete. Untrusted code: can't access the file system, can fetch Dhall libraries over HTTP(S) from static URLs (but libraries aren't allowed to access your data), can use up memory and CPU time for a DoS attack. Has a work-in-progress Clojure and Ruby implementation. |
| Java | [AbcDatalog](http://abcdatalog.seas.harvard.edu/) | Datalog | JVM&#39;s GC | 3-clause BSD | Implements Datalog. |
| Java | [BeanShell](https://github.com/beanshell/beanshell/) | Java | JVM&#39;s GC | Apache License 2.0 | An small, embeddable Java source code interpreter. Understands Java code with certain extensions like method closures. |
| Java | [Groovy](http://groovy-lang.org/) | Groovy | JVM&#39;s GC | Apache License 2.0 | A scripting language for the JVM. A large subset of Java is valid Groovy. [Integrating Groovy into applications](http://groovy-lang.org/integrating.html). |
| Java | [JRuby](http://www.jruby.org/) | Ruby | JVM&#39;s GC | Choice of EPL, GPL, and LGPL | An implementation of Ruby on the JVM. |
| Java | [JTcl](https://github.com/jtcl-project/jtcl) | Tcl | Ref. counting | Various BSD-like | Tcl 8.4 with some 8.5 features for the JVM. |
| Java | [Jython](http://www.jython.org/) | Python | JVM&#39;s GC | PSFL (BSD-like) | An implementation of Python on the JVM. |
| Java | [Kawa](https://www.gnu.org/software/kawa/) | Scheme | JVM&#39;s GC | MIT | R7RS. Supports the javax.script API. [Evaluating Scheme expressions from Java](https://www.gnu.org/software/kawa/Evaluating-Scheme-expressions-from-Java.html). |
| Java | [LuaJ](https://sourceforge.net/projects/luaj/) | Lua | JVM&#39;s GC | MIT | A Lua 5.2 spec-compliant interpreter written in Java for JME and JSE. Complies Lua directly to JVM bytecode. |
| Java | [NetRexx](http://www.netrexx.org/) | Rexx | JVM&#39;s GC | ICU (BSD-like) |  |
| Java | [Starlark (Java)](https://github.com/bazelbuild/bazel/tree/master/src/main/java/net/starlark/java) | Starlark | JVM&#39;s GC | Apache License 2.0 | Starlark for the JVM. The original implementation. |
| Object Pascal | [Pascal Script](http://www.remobjects.com/ps.aspx) | Pascal | None (manual MM) | modified zlib/libpng-License with mandatory attribution | Statically typed. Implements "most of Object Pascal". Can't define new classes. |
| Object Pascal (Delphi 2009 or later) | [DWScript](https://bitbucket.org/egrange/dwscript/) | DWScript | Ref. counting + cycle-detecting tracing GC | MPL 1.1, GPL 3 (JavaScript code generator) | [Description](https://www.delphitools.info/dwscript). A statically typed Delphi/Free Pascal-like language. Can compile to JavaScript. |
| OCaml | [Datalog (c-cube)](https://github.com/c-cube/datalog) | Datalog | OCaml&#39;s GC | 2-clause BSD | Implements Datalog. |
| OCaml | [Lua-ML](https://github.com/lindig/lua-ml) | Lua | OCaml&#39;s GC | 2-clause BSD | Embeddable Lua 2.5 reimplementation that integrates with OCaml type and module system. It's possible to extend or even replace the standard library with your own modules. |
| Rebol, Red, Red/System | [Red](https://github.com/red/red) | Red | Tracing | 3-clause BSD, BSL | A descendant of Rebol. Embeddable via [libRed](https://github.com/red/docs/blob/master/en/libred.adoc). Features a cross-platform native GUI system. Intended to have low memory usage. |
| Rust | [Dyon](https://github.com/pistondevelopers/dyon) | Dyon | None (Rust-style [lifetimes](http://www.piston.rs/dyon-tutorial/lifetimes.html)) | Apache License 2.0 or MIT | Has optional, optimistic (succeed-by-default) static type checking. |
| Rust | [gluon](https://github.com/gluon-lang/gluon) | gluon | Tracing | MIT | Statically typed. Inspired by Lua, Haskell, and OCaml. Each executing gluon thread gets a separate heap. |
| Rust | [Ketos](https://github.com/murarth/ketos) | Ketos | None (no heap allocation)? | Apache License 2.0 | A functional Lisp. |
| Rust | [Molt](https://github.com/wduquette/molt) | Tcl | Ref. counting | 3-clause BSD | A minimal Tcl implementation for Rust applications and libraries. |
| Rust | [Rhai](https://github.com/jonathandturner/rhai) | Rhai | None (Rust-style lifetimes) | MIT or Apache License 2.0 | An embedded scripting language for Rust inspired by ChaiScript. |
| Rust | [Starlark (Rust)](https://github.com/google/starlark-rust/) | Starlark | ? | Apache License 2.0 | Starlark in Rust. [Python bindings](https://github.com/inducer/starlark-pyo3). |
| Rust | [Wirefilter](https://github.com/cloudflare/wirefilter) | Wirefilter | None (no dynamic memory allocation) | MIT | An expression language for Wireshark-like filters. |

## See also

* [cwal: Scripting Engine Without A Language](https://fossil.wanderinghorse.net/r/cwal/home).
* [Game scripting languages benchmarked](https://github.com/r-lyeh/scriptorium).
* [Languages that compile to JavaScript](https://github.com/jashkenas/coffeescript/wiki/List-of-languages-that-compile-to-JS).
* [Languages that compile to Lua](https://github.com/hengestone/lua-languages).
* [miniKanren](http://minikanren.org/#implementations) logic programming language implementations.
* [sol](https://github.com/ThePhD/sol2) &mdash; C++ bindings for Lua.

## Contributing

Your contributions are welcome! See [CONTRIBUTING](CONTRIBUTING.md).

## License

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

## Disclosure

The curator of this document maintains Picol and has contributed to Jim Tcl.
