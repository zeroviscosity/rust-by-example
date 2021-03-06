The `Path` struct represents file paths in the underlying filesystem. There are
two flavors of `Path`: `posix::Path`, for UNIX-like systems, and
`windows::Path`, for Windows. The prelude exports the appropriate
platform-specific `Path` variant.

A `Path` can be created from almost any type that implements the
`BytesContainer` trait, like a string, and provides several methods to get
information from the file/directory the path points to.

Note that a `Path` is *not* internally represented as an UTF-8 string, but
instead is stored as a vector of bytes (`Vec<u8>`). Therefore, converting a
`Path` to a `&str` is *not* free and may fail (an `Option` is returned).

{path.play}

Be sure to check at other `Path` methods
([`posix::Path`][posix-path]
or [`windows::Path`][windows-path])
and the
[`FileStat`][file-stat]
struct.

[posix-path]: http://doc.rust-lang.org/std/path/posix/struct.Path.html
[windows-path]: http://doc.rust-lang.org/std/path/windows/struct.Path.html
[file-stat]: http://doc.rust-lang.org/std/io/struct.FileStat.html
