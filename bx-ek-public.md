Create an encrypted public key from an intermediate passphrase token (BIP38).
```sh
$ bx ek-public --help
```
```
Usage: bx ek-public [-hu] [--config VALUE] [--version VALUE] TOKEN [SEED]

Info: Create an encrypted public key from an intermediate passphrase     
token (BIP38).                                                           

Options (named):

-c [--config]        The path to the configuration settings file.        
-h [--help]          Get a description and instructions for this command.
-u [--uncompressed]  Use the uncompressed public key format, as used to  
                     create the corresponding encrypted private key.     
-v [--version]       The desired payment address version used to create  
                     the corresponding encrypted private key.            

Arguments (positional):

TOKEN                The intermediate passphrase token used to create the
                     corresponding encrypted private key.                
SEED                 The Base16 entropy for the new encrypted public key.
                     Must be at least 192 bits in length (only the first 
                     192 bits are used). If not specified the seed is    
                     read from STDIN.   
```
The `--version` option is a [libbitcoin enhancement](https://github.com/libbitcoin/libbitcoin/wiki/Altchain-Encrypted-Private-Keys) not yet specified in [BIP-38](https://github.com/bitcoin/bips/blob/master/bip-0038.mediawiki).

See also [token-new](bx-token-new), [ek-new](bx-ek-new) and [ek-address](bx-ek-address).
### Example 1
lot/sequence
```sh
$ bx ek-public passphrasecpXbDpHuo8F7yuZqR49koDA9uQojPijjjZaxsar7Woo9pfHJbeWF3VMU9EPBqJ baadf00dbaadf00dbaadf00dbaadf00dbaadf00dbaadf00d
```
```
cfrm38VXASNzNjsak8pLc3ZtyPnBNDxAAbB18KMMCSjf8ZhW3FVTeuw2r9J3tyAUNyhfM7VMZuP
```
### Example 2
```sh
$ bx ek-public passphraseryQXuRZZQ3Jw5rAT7m6MzxkGSSRmysq3Ayj9vuEHEnbVPJSmRQ2xYFKDKjGYrq baadf00dbaadf00dbaadf00dbaadf00dbaadf00dbaadf00d
```
```
cfrm38VUVm4ZGXku7wWGiLfAJNoeDHConFb9CugfTnR1SQC1jf3uwyKULmCMk4SUhsXasMyPcA9
```
### Example 3
piped commands
```sh
$ bx seed | bx ek-public passphraseryQXuRZZQ3Jw5rAT7m6MzxkGSSRmysq3Ayj9vuEHEnbVPJSmRQ2xYFKDKjGYrq
```
```
7113f4c2e8f67b61225c9a619cd984b63f28df434bf18217 
cfrm38VURwDvZXxV2AfWnHe6GwDxSG4FkrK4en7VdaxLPMxMnU8BaLneNVAwf19TAkbmAptNNaH
```
### Example 4
invalid seed
```sh
$ bx ek-public passphraseryQXuRZZQ3Jw5rAT7m6MzxkGSSRmysq3Ayj9vuEHEnbVPJSmRQ2xYFKDKjGYrq baadf00dbaadf00dbaadf00dbaadf00d
```
```
The seed is less than 192 bits long.
```
### Example 5
--uncompressed
```sh
$ bx ek-public -u passphraseryQXuRZZQ3Jw5rAT7m6MzxkGSSRmysq3Ayj9vuEHEnbVPJSmRQ2xYFKDKjGYrq baadf00dbaadf00dbaadf00dbaadf00dbaadf00dbaadf00d
```
```
cfrm38V5FtqpFoBNE9wpKjp5Fe97tM7YX6brNPCjpb9uLiqENKfeHHUKLd2VrvQhuHVUwgNVaSt
```
### Example 6
--version 111 (testnet)
```sh
$ bx ek-public -v 111 passphraseryQXuRZZQ3Jw5rAT7m6MzxkGSSRmysq3Ayj9vuEHEnbVPJSmRQ2xYFKDKjGYrq baadf00dbaadf00dbaadf00dbaadf00dbaadf00dbaadf00d
```
```
cfrm2zc7BCp4KwhEE6HzSSxVhUyj2ky8bzvSLEqmAPcakQXb49uFQ87UEg8EhbuwA33t8db2fYW
```
### Example 7
--version 111 (testnet), --uncompressed
```sh
$ bx ek-public -u -v 111 passphraseryQXuRZZQ3Jw5rAT7m6MzxkGSSRmysq3Ayj9vuEHEnbVPJSmRQ2xYFKDKjGYrq baadf00dbaadf00dbaadf00dbaadf00dbaadf00dbaadf00d
```
```
cfrm2zbi4iuQJ7cY69uJZsxhYLk4wLY7UWQiZ1wH5b3pEnzczSH3GHY3hAyV5AiWmU7mpk2Bqqc
```