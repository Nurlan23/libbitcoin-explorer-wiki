Watch the network for all blocks.

```sh
$ bx subscribe-block --help
```
```
Usage: bx subscribe-block [-h] [--config value] [--duration value]       
[--format value] [SERVER-URL]                                            

Info: Watch the network for all blocks. Requires a Libbitcoin server     
connection.                                                              

Options (named):

-c [--config]        The path to the configuration settings file.        
-d [--duration]      The duration of the subscription in seconds,        
                     defaults to 600.                                    
-f [--format]        The output format. Options are 'info', 'json' and   
                     'xml', defaults to 'info'.                          
-h [--help]          Get a description and instructions for this command.

Arguments (positional):

SERVER-URL           The URL of the Libbitcoin server to use. If not     
                     specified the URL is obtained from configuration    
                     settings or defaults.   
```
This command supports [configuration settings](Configuration-Settings).

### Example 1

```sh
$ bx subscribe-block
header
{
    bits 388503969
    hash 000000000000000000059769b4c18ca9960f09f7230b2396b89f36148aa599c9
    merkle_tree_hash f2847a518bdbf4848366884c132c05bacc4b058e3e6fa079b446f6c50e8dea81
    nonce 458599866
    previous_block_hash 000000000000000000161d22d504e0abc5b000755b1b74999416076e0b1ce55e
    time_stamp 1537192510
    version 536870912
}
```

### Example 2

This command can accept an optional block service URL on the command line:

```sh
$ bx subscribe-block tcp://mainnet2.libbitcoin.net:9093
header
{
    bits 388503969
    hash 000000000000000000059769b4c18ca9960f09f7230b2396b89f36148aa599c9
    merkle_tree_hash f2847a518bdbf4848366884c132c05bacc4b058e3e6fa079b446f6c50e8dea81
    nonce 458599866
    previous_block_hash 000000000000000000161d22d504e0abc5b000755b1b74999416076e0b1ce55e
    time_stamp 1537192510
    version 536870912
}
```