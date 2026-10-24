# Security policy

This policy covers every repository in the turf-lang organization: the
compiler and its runtime and standard library (`turf-lang`), the `turf` tool
(`turf-cli`), the language server (`turf-lsp`), `turf-fuzz`, the installers
and package recipes, and the website.

## What to report privately

Turf promises that safe Turf code cannot corrupt memory, and that the
boundaries around unsafe code hold. Report privately anything that breaks
those promises in a way that could be used against someone who builds or runs
a Turf program:

- **Memory corruption from safe code**: a program with no `unsafe` block and
  no `unsafe module;` that reads or writes memory it should not, uses memory
  after it is freed, or corrupts the heap.
- **A check that can be bypassed**: a bounds, null, overflow or escape check
  that safe code can get around, or one the optimizer removes when it should
  not.
- **A boundary that does not hold**: a way past `[unsafe] allow`, `turf audit`
  or the raw-pointer capability, so that unsafe code runs in a package that
  was never allowed it.
- **The runtime and garbage collector**: an object freed while still
  reachable, or a way to make the collector free memory it does not own.
- **The toolchain itself**: a source file, package, manifest or lock file that
  makes `turf`, `turfc` or `turf-lsp` run code, read or write files outside
  the project, or fetch something other than what `turf.lock` pins; a flaw in
  the installers or release archives.

If you are not sure whether something is a security problem, report it
privately. We would rather move a report to a public issue than the other way
around.

These are ordinary bugs; please open a public issue for them:

- the compiler crashing, hanging or rejecting a valid program;
- a wrong or unclear error message;
- a bug inside code that is marked `unsafe` or in C called through
  `extern fn`, where Turf's documentation already says the responsibility is
  the programmer's.

## How to report

Use GitHub's private vulnerability reporting: open the **Security** tab of the
affected repository and choose **Report a vulnerability**. For the compiler,
that is
[github.com/turf-lang/turf-lang/security/advisories/new](https://github.com/turf-lang/turf-lang/security/advisories/new).
Only the maintainers can see the report.

The most useful report has:

- the smallest program or input that shows the problem;
- the output of `turf version`, and your platform;
- what you expected, and what happened instead.

Please do not open a public issue, pull request or discussion about the
problem until it is fixed.

## What happens next

- We aim to reply within a week, and to tell you whether we can reproduce it.
- We fix it, and add the reproducer as a test in the same change, so it
  cannot quietly come back.
- We publish a GitHub security advisory and name the fix in the release
  notes. We credit you there unless you ask us not to.
- We will agree a disclosure date with you. Turf is a small project, so please
  give us a reasonable time before you publish your own write-up.

Turf has no bug bounty. We are grateful for every report all the same.

## Supported versions

Security fixes go into the latest release line, as a patch release
(`2.N.P`). Older lines are not patched; upgrading to the latest patch is the
fix. When 3.0 is released, the last 2.x line will receive security and
soundness fixes for six months.
