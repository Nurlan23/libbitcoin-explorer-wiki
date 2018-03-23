Get the last block height.
```sh
$ bx fetch-height --help
```
```
Usage: bx fetch-height [-h] [--config value] [SERVER-URL] [PUBLIC-KEY]

Info: Get the last block height. Requires a Libbitcoin server connection.

Options (named):

-c [--config]        The path to the configuration settings file.
-h [--help]          Get a description and instructions for this command.

Arguments (positional):

SERVER-URL           The URL of the Libbitcoin server to use. If not
                     specified the URL is obtained from configuration
                     settings or defaults.
PUBLIC-KEY           The public key of the Libbitcoin server. If not
                     specified the key is obtained from configuration
                     settings or defaults.
```
This command supports [configuration settings](Configuration-Settings).

The height reported will increase as more blocks are mined and may vary slightly between servers.
### Example 1
```sh
$ bx fetch-height
```
```
325956
```
### Example 2
Specified server-url
```sh
$ bx fetch-height tcp://mainnet.libbitcoin.net:9091
```
```
514826
```

### Example 3
Specified server-url and public key (see [here](https://github.com/libbitcoin/libbitcoin-server/wiki/Community-Servers) for more details)
```sh
$ bx fetch-height tcp://mainnet2.libbitcoin.net:9081 "}[YQ:ks:iKd0F1!ycPgj:4CVzfV-=jsF}x&%ff=/"
```
```
514826
```

### Example 4
Specified server-url with an incorrect port number
```sh
$ bx fetch-height tcp://obelisk.unsystem.net
```
```
timed out
```