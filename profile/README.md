<h3 align="center">A statically typed language that compiles ahead of time to native executables.</h3>

<p align="center">
  <a href="https://turflang.org">Website</a> ·
  <a href="https://turflang.org/download">Download</a> ·
  <a href="https://github.com/turf-lang/turf-lang/releases">Releases</a> ·
  <a href="https://github.com/turf-lang/turf-lang/issues">Issues</a>
</p>

## About Turf

Turf is a compiled language built on LLVM. It has structs, enums, real
generics, state machines, pattern matching, error unions, and a
garbage-collected heap with checked references. The standard library covers
strings, collections, files, JSON, HTTP and sockets. A project and package tool
and a language server ship with it.

Programs compile to a single native executable that needs no Turf files at run
time. Releases are self-contained on Linux (x86-64, arm64), macOS (Apple
Silicon) and Windows (x86-64): the archive carries the compiler, its LLVM, the
linker and the runtime, so there is nothing else to install.

## Get started

```sh
# Linux and macOS
curl -fsSL https://turflang.org/install.sh | sh
```

```powershell
# Windows (PowerShell)
irm https://turflang.org/install.ps1 | iex
```

Or use a package manager:

```sh
brew install turf-lang/turf/turf        # Homebrew
scoop bucket add turf https://github.com/turf-lang/scoop-turf
scoop install turf                      # Scoop
```

Then:

```sh
turf new hello && cd hello
turf run
```

## Repositories

| Repository | What it is |
|---|---|
| [**turf-lang**](https://github.com/turf-lang/turf-lang) | The compiler, standard library and language reference. Start here. |
| [**turf-cli**](https://github.com/turf-lang/turf-cli) | The `turf` command-line tool: projects, builds, tests, formatting and dependencies. |
| [**turf-lsp**](https://github.com/turf-lang/turf-lsp) | The language server, which runs the real compiler in-process for diagnostics, hover and completion. |
| [**turf-skills**](https://github.com/turf-lang/turf-skills) | Skills that teach coding agents to write Turf. |
| [**turf-fuzz**](https://github.com/turf-lang/turf-fuzz) | Fuzzing for the compiler, with findings promoted to regression tests. |
| [**website**](https://github.com/turf-lang/website) | Source for [turflang.org](https://turflang.org). |
| [**homebrew-turf**](https://github.com/turf-lang/homebrew-turf) | Homebrew tap. |
| [**scoop-turf**](https://github.com/turf-lang/scoop-turf) | Scoop bucket for Windows. |

## Contributing

Bug reports, questions and pull requests are welcome. Report a compiler bug on
[turf-lang](https://github.com/turf-lang/turf-lang/issues) and include the
output of `turf version`. Problems with the `turf` tool belong on
[turf-cli](https://github.com/turf-lang/turf-cli/issues), and editor problems
on [turf-lsp](https://github.com/turf-lang/turf-lsp/issues). Each repository's
README says how to build and test it.
