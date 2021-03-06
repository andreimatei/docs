---
title: Cockroach Commands
toc: false
---

This page lists the `cockroach` commands for configuring, starting, and managing a CockroachDB cluster. Click a command for supported flags and examples. See [logging flags](#logging-flags) for flags that can be set on any command. 

You can run `./cockroach help` in your shell to get similar guidance.

Command | Usage
--------|----
[`start`](start-a-node.html) | Start a node.
[`cert`](create-security-certificates.html) | Create CA, node, and client certificates.
[`sql`](use-the-built-in-sql-client.html) | Use the built-in SQL client.
[`quit`](stop-a-node.html) | Drain and shutdown a node.
`exterminate` | Destroy all data held by a node.
`zone` | Get, set, list, and remove zones.
`node` | List nodes and show their status.
`gen` | Generate manpages and bash completion file.
`version` | Output CockroachDB version information.
`debug` | Extract data from files of a failed process.

## Logging Flags

By default, CockroachDB logs all messages and errors to files (see `--log-dir`) and copies errors with a severity of `error` or higher to the standard error stream (see `--alsologtostderr`). 

Flag | Description
-----|------------
`--alsologtostderr` | Copy log messages at or above this severity level to the standard error stream in addition to log files. Possible values: `info`, `warning`, `error`, and `fatal`. <br><br>**Default:** `error`
`--log-dir` | Write log files in this directory. <br><br> **Default:** `<first-store-dir>/logs` for the `start` command; `$TMPDIR` for all other commands  
`--logtostderr` |  Write log messages of all severities to the standard error stream and not to log files. If this flag is set, `--log-dir` and `--alsologtostderr` are ignored. Possible values: `true` or `false`.<br><br>**Default:** `false`
`--no-color` | Do not colorize the standard error stream based on severity. Possible values: `true` or `false`. <br><br>**Default:** `false`   

The `--log-backtrace-at`, `--verbosity`, and `--vmodule` flags are intended for internal debugging. 