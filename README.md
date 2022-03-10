# lnav-demo

Demo for the [NSWI126](https://d3s.mff.cuni.cz/cz/teaching/nswi126/) subject.

## lnav - The Logfile Navigator

> **https://lnav.org/**

## Install

> https://lnav.org/downloads

## Demo

### Example log files

System log files (gzipped):
```
$ journalctl > journalctl.log
```

Strace of python invocation:
```
$ 2>strace-python.log strace -tt -T python
```

### Basics

1. Launch `lnav`
```
$ lnav .
```

2. Get Help - `?`

3. Movement - arrows | `hjkl` | `PgDown|Space` and `PgUp|Backspace`

4. `TAB`

5. `:open`

6. `q` quit, but there are Sessions

7. `CTRL-R` reset the session

### Basic Querying

1. `?` -> `/` -> `^Query`

### Time movement

1. `?` -> `/` -> `Chronological Navigation`
### Bookmarks

1. `?` -> `/` -> `^Bookmarks`

2. `m` -> move -> `M` -> `c` -> use your clipboard

### Filtering 

1. `TAB` -> `i` for filter-in / `o` for filter-out -> `SPACE` for toggle

2. accidental quit `q` -> re-open -> session restored -> reset the session `CTRL-R`

### SQL mode

1. `;`

2. `;.schema` -> `/syslog_log` -> `n`

3. `;select * from syslog_log;`

4. `;select log_procname, count(*) from syslog_log group by log_procname;`

5. `;select syscall, count(*) from strace_log group by syscall;` for syscall log

6. apply that on top of filter, `v` to switch to query result display

### Display options

1. `?` -> `/` -> `Display options`

2. `T` - time passed

3. `i` and `I` - log frequency histogram

### Specials

1. `goto <line#|N%|abs-time|relative-time>`

2. `:comment comment`

3. `:tag comment` -> search for it

4. `:hide-lines-after <date>` -> `:show*`

5. `o/O` - follow next/previous context

6. scripting, filter sharing...

### Custom log format

Out of the box supported file formats:
> https://docs.lnav.org/en/latest/formats.html

Defining your own format to enable navigation and advanced querying:
> https://docs.lnav.org/en/latest/formats.html#defining-a-new-format
