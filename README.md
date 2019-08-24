### reload executable
> After changing program, reload executable with _file_ command
```
(gdb) file gdbprog
```

### pass command-line arguments

```
(gdb) run arg1 arg2 arg3...
```

```
gdb -ex=run --args executable arg1 arg2 arg3...
```

```
gdb --eval-command=run --args executable arg1 arg2 arg3...
```

```
(gdb) set args arg1 arg2 arg3...
(gdb) run
```
> :warning: If the `run` command followed by some arguments like `arg11 arg12`, the **args** set by the `set` command will be **overridden**.

> :warning: Although `set a arg1 arg2 ` will throw an warning of ambiguous set command "a arg1 arg2": **a**da, **a**gent, **a**nnotate, **a**rchitecture, **a**rgs, **a**uto-connect-native-target, **a**uto-load..., the `set arg arg1 arg2` works.

> Furthermore, `set ar arg1 arg2`, Ambiguous set command "ar arg1 arg2": **ar**chitecture, **arg**s.

```
gdb -ex "set args arg1 arg2..." -ex "r" executable
```

### print with x command
> **x** /[_Length_][_Format_] [_Address expression_]

If specified, allows overriding the output format used by the command. Valid **format specifiers** are:
-   o - octal
-   x - hexadecimal
-   d - decimal
-   u - unsigned decimal
-   t - binary
-   f - floating point
-   a - address
-   c - char
-   s - string
-   i - instruction

The following **size modifiers** are supported:

-   b - byte
-   h - halfword (16-bit value)
-   w - word (32-bit value)
-   g - giant word (64-bit value)

```
(gdb) x/16bx array
```
