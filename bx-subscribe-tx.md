Watch the network for all transactions.

```sh
$ bx subscribe-tx --help
```
```
Usage: bx subscribe-tx [-h] [--config value] [--duration value] [--format
value] [SERVER-URL]                                                      

Info: Watch the network for all transactions. Requires a Libbitcoin      
server connection.                                                       

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
$ bx subscribe-tx
35c4bc4e87e790836e8531fdf1b7194daac69a43708a69855ebe824589a69571
1a2e1abea77f1b74c8f45565450ff6582c9f2b71d8cb8c3c59f740f1bd7f1a07
c82e339c8b4797e2e29b2e5c1a27859eec1c649f3b24e4ddb217c160eff5c259
ce752eaf8615ba02d30eb9c94a006c29886c9eae26633f7d1e0f29461c425d75
9fe198978e3ae8f069e9916f7a40f8f64fa815f8c250ea531ea0d52a9628de91
... snip ...
```

### Example 2

This command can accept an optional transaction service URL on the command line:

```sh
$ bx subscribe-tx tcp://mainnet2.libbitcoin.net:9094
838c2ab566a2723c554fbfdeaef1ab1ef9d20d5ce6706c2245ac04d3d84a6923
e2dcbdd3a71f7d99a6e7da83db74bf65bd54f8e27fb30d546bd785c865b28460
36b652793a4a20d727201a20595285495065855db4dfbaf6ce0fabe994ca5251
264349f47328f732a1e8eb59ff5eacc15db6e2615abf8efecc2dfde4d7acec3e
243aeaba2a0deae1eac89f41c7984dad0efb02a9c7892f2ea9e0dc58bcfa9faf
6cf8d28470b8a622ecd54584853b6e83c6c900ab5dfa8b8e353bb4a87a331440
293bf3e32adf35cb3a373e1720986cb8a4a901b2a49d0caceb04973acd8eddff
e5a7f56deb846edeca6abe43a5ca8198e610f371e13f0492be91d8a9bfb08e20
... snip ...
```