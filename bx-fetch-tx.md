Get transactions by hash.
```sh
$ bx fetch-tx --help
```
```
Usage: bx fetch-tx [-h] [--config value] [--format value] [HASH]

Info: Get a transaction by its hash. Requires a Libbitcoin server
connection.

Options (named):

-c [--config]        The path to the configuration settings file.
-f [--format]        The output format. Options are 'info', 'json' and
                     'xml', defaults to 'info'.
-h [--help]          Get a description and instructions for this command.
-w [--witness]       Include witness as applicable. Requires a version
                     3.4 or later Libbitcoin server connection.
Arguments (positional):

HASH                 The Base16 transaction hash of the transaction to
                     get. If not specified the transaction hash is read
                     from STDIN.
```
This command supports [configuration settings](Configuration-Settings).
### Example 1
[Satoshi's words](http://www.thetimes.co.uk/tto/business/industries/banking/article2160028.ece)
```sh
$ bx fetch-tx 4a5e1e4baab89f3a32518a88c31bc87f618f76673e2cc77ab2127b7afdeda33b
```
```
transaction
{
    hash 4a5e1e4baab89f3a32518a88c31bc87f618f76673e2cc77ab2127b7afdeda33b
    inputs
    {
        input
        {
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
            address 1A1zP1eP5QGefi2DMPTfTL5SLmv7DivfNa
            script "[04678afdb0fe5548271967f1a67130b7105cd6a828e03909a67962e0ea1f61deb649f6bc3f4cef38c4f35504e51ec112de5c384df7ba0b8d578a4c702b6bf11d5f] checksig"
            value 5000000000
        }
    }
    version 1
}
```
From `transaction.inputs.input.script[2]` above:
```sh
$ bx base16-decode 5468652054696d65732030332f4a616e2f32303039204368616e63656c6c6f72206f6e206272696e6b206f66207365636f6e64206261696c6f757420666f722062616e6b73
```
```
The Times 03/Jan/2009 Chancellor on brink of second bailout for banks
```
### Example 2
--format json, [first WikiLeaks transaction](https://blockchain.info/tx/4eed9092aaf8cc8a527570546816a752d5fe825244c25c8e26084fc80b06b588)
```sh
$ bx fetch-tx -f json 4eed9092aaf8cc8a527570546816a752d5fe825244c25c8e26084fc80b06b588
```
```
{
    "transaction": {
        "hash": "4eed9092aaf8cc8a527570546816a752d5fe825244c25c8e26084fc80b06b588",
        "inputs": [
            {
                "address_hash": "16fdb37edae340402c9e037a08eb109dfbb7eeee",
                "previous_output": {
                    "hash": "e58f3fb6e2ebe8e74e5af032dfd8c8e5e51f53d59489591a71599a80bdca910d",
                    "index": "0"
                },
                "script": "[304502210092947e1d588378cd215c2d3990b862cf368657741b5941c3cadf87a46b5a211d02205ef4ba2c1f35886e4272250a2abec2d1f2f21d5c581bf3eb5fc27b5be332660701] [04aefca2b53d176aa22f730a5497eb32011e15387c63a75780efeb21e981e9728033808732a321b48a8e0e2a5f9c1efb745dd41e9c92c6260daad567544b122446]",
                "sequence": "4294967295"
            },
            {
                "address_hash": "40ab191b6886a477608f6253b57fde4f63f8c288",
                "previous_output": {
                    "hash": "203609ba699c1f56e4a8d793a8cd746aa5aa5fc2e71205cf67a94487b45bafa9",
                    "index": "1"
                },
                "script": "[3045022100b7e63179ce698082c0f97c4ba6e24f5c7b7d37e5098c1b46674d03ef17a68b8d022008ebc699df19f11a11e76320719d7c139bb10ce9aa255f674a44b95f54053d9d01] [04c8f5fbadfe4534eaa3e2ec49dd797aaa43cb13d669dbd6ab769ea45a5ebcdacc6aee8e0e75fec2cb7fa088e16ead1a979f394b5af9e0d2998b6dc5bb6c41b005]",
                "sequence": "4294967295"
            }
        ],
        "lock_time": "0",
        "outputs": [
            {
                "address_hash": "b169f2b0b866db05900b93a5d76345f18d3afb24",
                "script": "dup hash160 [b169f2b0b866db05900b93a5d76345f18d3afb24] equalverify checksig",
                "value": "7500000"
            },
            {
                "address_hash": "3f156517411bd0ea2f22e2f42d6846b405facb27",
                "script": "dup hash160 [3f156517411bd0ea2f22e2f42d6846b405facb27] equalverify checksig",
                "value": "97317"
            }
        ],
        "version": "1"
    }
}
```
### Example 3
redirect to file, [DPR Seized Coins #1](https://blockchain.info/tx/e3d6fe810f79b293705ed6e587951332c545a87fac860278b2ad4447106bb789) 
```sh
$ bx fetch-tx -f xml e3d6fe810f79b293705ed6e587951332c545a87fac860278b2ad4447106bb789 > dpr1.xml
```