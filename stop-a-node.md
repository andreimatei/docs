---
title: Stop a Node
toc: false
---

To stop a CockroachDB node running in the background, run the `cockroach quit` command with appropriate flags. To stop a node running in the foreground, use **control + c** or run `cockroach quit` from another shell. 

The `quit` command allows in-flight requests to complete and then shuts down the node. Once a node has been offline for approximately 5 minutes, CockroachDB automatically rebalances replicas from the missing node, using unaffected replicas on other nodes as sources. 

<div id="toc"></div>

## Synopsis

~~~ shell
# Stop a node:
$ ./cockroach quit <flags>

# View help:
$ ./cockroach help quit
~~~

## Flags

The `quit` command supports the following flags as well as [logging flags](cockroach-commands.html#logging-flags).


Flag | Description 
-----|------------
`--ca-cert` | The path to the [CA certificate](create-security-certificates.html). If the cluster was started without the `--insecure` flag, this flag is required. 
`--cert` | The path to the [node certificate](create-security-certificates.html). If the cluster was started without the `--insecure` flag, this flag is required.
`--host` | A valid address for reaching the node. <br><br>**Default:** localhost
`--http-port` | The port that the node listens on for HTTP requests. <br><br>**Default:** 8080
`--insecure` | Whether or not the cluster is secure (authentication and encrypted client/node and inter-node communication). If the cluster is secure, set the `--ca-cert`, `--cert`, and `--key` flags but leave this flag out. If the cluster is insecure, set this flag.
`--key` | The path to [node key](create-security-certificates.html) protecting the node certificate. If the cluster was started without the `--insecure` flag, this flag is required. 

## Examples

#### Shut down a node

~~~ shell
# Secure:
$ ./cockroach quit --ca-cert=certs/ca.cert --cert=certs/node.cert --key=certs/node.key --host=nodehostname.com --http-port=8081

# Insecure:
$ ./cockroach quit --insecure --host=nodehostname.com --http-port=8081
~~~