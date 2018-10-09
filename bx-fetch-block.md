Get the block from the specified hash or height. Height is ignored if both are specified.
```sh
$ bx fetch-block --help
```
```
Usage: bx fetch-block [-h] [--config value] [--format value] [--hash     
value] [--height value]                                                  

Info: Get the block from the specified hash or height. Height is ignored 
if both are specified. Requires a Libbitcoin server connection.          

Options (named):

-c [--config]        The path to the configuration settings file.        
-f [--format]        The output format. Options are 'info', 'json' and   
                     'xml', defaults to 'info'.                          
-h [--help]          Get a description and instructions for this command.
-s [--hash]          The Base16 block hash.                              
-t [--height]        The block height.
```
This command supports [configuration settings](Configuration-Settings).
### Example 1
--height 0
```sh
$ bx fetch-block
```
```
block
{
    bits 486604799
    hash 000000000019d6689c085ae165831e934ff763ae46a2a6c172b3f1b60a8ce26f
    merkle_tree_hash 4a5e1e4baab89f3a32518a88c31bc87f618f76673e2cc77ab2127b7afdeda33b
    nonce 2083236893
    previous_block_hash 0000000000000000000000000000000000000000000000000000000000000000
    time_stamp 1231006505
    version 1
    transactions
    {
        transaction
        {
            hash 4a5e1e4baab89f3a32518a88c31bc87f618f76673e2cc77ab2127b7afdeda33b
            inputs
            {
                input
                {
                    address_hash 5b19778555f776292926b8dd581e1b9d2ab7cbbb
                    previous_output
                    {
                        hash 0000000000000000000000000000000000000000000000000000000000000000
                        index 4294967295
                    }
                    script "[ffff001d] [04] [5468652054696d65732030332f4a616e2f32303039204368616e63656c6c6f72206f6e206272696e6b206f66207365636f6e64206261696c6f757420666f722062616e6b73]"
                    sequence 4294967295
                }
            }
            lock_time 0
            outputs
            {
                output
                {
                    address_hash 62e907b15cbf27d5425399ebf6f0fb50ebb88f18
                    script "[04678afdb0fe5548271967f1a67130b7105cd6a828e03909a67962e0ea1f61deb649f6bc3f4cef38c4f35504e51ec112de5c384df7ba0b8d578a4c702b6bf11d5f] checksig"
                    value 5000000000
                }
            }
            version 1
        }
    }
}
```
### Example 2
--height 1
```sh
$ bx fetch-block -t 1
```
```
block
{
    bits 486604799
    hash 00000000839a8e6886ab5951d76f411475428afc90947ee320161bbf18eb6048
    merkle_tree_hash 0e3e2357e806b6cdb1f70b54c3a3a17b6714ee1f0e68bebb44a74b1efd512098
    nonce 2573394689
    previous_block_hash 000000000019d6689c085ae165831e934ff763ae46a2a6c172b3f1b60a8ce26f
    time_stamp 1231469665
    version 1
    transactions
    {
        transaction
        {
            hash 0e3e2357e806b6cdb1f70b54c3a3a17b6714ee1f0e68bebb44a74b1efd512098
            inputs
            {
                input
                {
                    address_hash 6d4c0aa972c314840ac07be96c5dde9c714c9ca4
                    previous_output
                    {
                        hash 0000000000000000000000000000000000000000000000000000000000000000
                        index 4294967295
                    }
                    script "[ffff001d] [04]"
                    sequence 4294967295
                }
            }
            lock_time 0
            outputs
            {
                output
                {
                    address_hash 119b098e2e980a229e139a9ed01a469e518e6f26
                    script "[0496b538e853519c726a2c91e61ec11600ae1390813a627c66fb8be7947be63c52da7589379515d4e0a604f8141781e62294721166bf621e73a82cbf2342c858ee] checksig"
                    value 5000000000
                }
            }
            version 1
        }
    }
}
```

> Notice that the `block.previous_block_hash` property matches the `block.hash` property returned for the height 0 request.

### Example 3
--hash [[genesis block hash](https://en.bitcoin.it/wiki/Genesis_block)]
```sh
$ bx fetch-block -s 000000000019d6689c085ae165831e934ff763ae46a2a6c172b3f1b60a8ce26f
```
```
block
{
    bits 486604799
    hash 000000000019d6689c085ae165831e934ff763ae46a2a6c172b3f1b60a8ce26f
    merkle_tree_hash 4a5e1e4baab89f3a32518a88c31bc87f618f76673e2cc77ab2127b7afdeda33b
    nonce 2083236893
    previous_block_hash 0000000000000000000000000000000000000000000000000000000000000000
    time_stamp 1231006505
    version 1
    transactions
    {
        transaction
        {
            hash 4a5e1e4baab89f3a32518a88c31bc87f618f76673e2cc77ab2127b7afdeda33b
            inputs
            {
                input
                {
                    address_hash 5b19778555f776292926b8dd581e1b9d2ab7cbbb
                    previous_output
                    {
                        hash 0000000000000000000000000000000000000000000000000000000000000000
                        index 4294967295
                    }
                    script "[ffff001d] [04] [5468652054696d65732030332f4a616e2f32303039204368616e63656c6c6f72206f6e206272696e6b206f66207365636f6e64206261696c6f757420666f722062616e6b73]"
                    sequence 4294967295
                }
            }
            lock_time 0
            outputs
            {
                output
                {
                    address_hash 62e907b15cbf27d5425399ebf6f0fb50ebb88f18
                    script "[04678afdb0fe5548271967f1a67130b7105cd6a828e03909a67962e0ea1f61deb649f6bc3f4cef38c4f35504e51ec112de5c384df7ba0b8d578a4c702b6bf11d5f] checksig"
                    value 5000000000
                }
            }
            version 1
        }
    }
}
```
### Example 4
--height 1 --hash [[genesis block hash](https://en.bitcoin.it/wiki/Genesis_block)]
```sh
$ bx fetch-block -t 1 -s 000000000019d6689c085ae165831e934ff763ae46a2a6c172b3f1b60a8ce26f
```
```
block
{
    bits 486604799
    hash 000000000019d6689c085ae165831e934ff763ae46a2a6c172b3f1b60a8ce26f
    merkle_tree_hash 4a5e1e4baab89f3a32518a88c31bc87f618f76673e2cc77ab2127b7afdeda33b
    nonce 2083236893
    previous_block_hash 0000000000000000000000000000000000000000000000000000000000000000
    time_stamp 1231006505
    version 1
    transactions
    {
        transaction
        {
            hash 4a5e1e4baab89f3a32518a88c31bc87f618f76673e2cc77ab2127b7afdeda33b
            inputs
            {
                input
                {
                    address_hash 5b19778555f776292926b8dd581e1b9d2ab7cbbb
                    previous_output
                    {
                        hash 0000000000000000000000000000000000000000000000000000000000000000
                        index 4294967295
                    }
                    script "[ffff001d] [04] [5468652054696d65732030332f4a616e2f32303039204368616e63656c6c6f72206f6e206272696e6b206f66207365636f6e64206261696c6f757420666f722062616e6b73]"
                    sequence 4294967295
                }
            }
            lock_time 0
            outputs
            {
                output
                {
                    address_hash 62e907b15cbf27d5425399ebf6f0fb50ebb88f18
                    script "[04678afdb0fe5548271967f1a67130b7105cd6a828e03909a67962e0ea1f61deb649f6bc3f4cef38c4f35504e51ec112de5c384df7ba0b8d578a4c702b6bf11d5f] checksig"
                    value 5000000000
                }
            }
            version 1
        }
    }
}
```

> The genesis block is height 0. Notice that height is ignored when both hash and height are specified. To test a height against a hash request the hash based on height alone and then compare the hash value against the returned `block.hash` property.