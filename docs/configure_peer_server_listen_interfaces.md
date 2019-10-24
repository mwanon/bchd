bchd allows you to bind to specific interfaces which enables you to setup
configurations with varying levels of complexity.  The listen parameter can be
specified on the command line as shown below with the -- prefix or in the
configuration file without the -- prefix (as can all long command line options).
The configuration file takes one entry per line.

**NOTE:** The listen flag can be specified multiple times to listen on multiple
interfaces as a couple of the examples below illustrate.

Command Line Examples:

|Flags|Comment|
|----------|------------|
|--listen=|all interfaces on default port which is changed by `--testnet` and `--regtest` (**default**)|
|--listen=0.0.0.0|all IPv4 interfaces on default port which is changed by `--testnet` and `--regtest`|
|--listen=::|all IPv6 interfaces on default port which is changed by `--testnet` and `--regtest`|
|--listen=:8456|all interfaces on port 8456|
|--listen=0.0.0.0:8456|all IPv4 interfaces on port 8456|
|--listen=[::]:8456|all IPv6 interfaces on port 8456|
|--listen=127.0.0.1:8456|only IPv4 localhost on port 8456|
|--listen=[::1]:8456|only IPv6 localhost on port 8456|
|--listen=:8456|all interfaces on non-standard port 8456|
|--listen=0.0.0.0:8456|all IPv4 interfaces on non-standard port 8456|
|--listen=[::]:8456|all IPv6 interfaces on non-standard port 8456|
|--listen=127.0.0.1:8457 --listen=[::1]:8456|IPv4 localhost on port 8457 and IPv6 localhost on port 8456|
|--listen=:8456 --listen=:8457|all interfaces on ports 8456 and 8457|

The following config file would configure bchd to only listen on localhost for both IPv4 and IPv6:

```text
[Application Options]

listen=127.0.0.1:8456
listen=[::1]:8456
```

In addition, if you are starting btcd with TLS and want to make it
available via a hostname, then you will need to generate the TLS
certificates for that host. For example,
 ```
gencerts --host=myhostname.example.com --directory=/home/user/.bchd/
```
