Convert a mnemonic seed (Electrum) to its numeric representation.

```sh
$ bx electrum-to-seed --help
```
```
Usage: bx electrum-to-seed [-h] [--config value] [--language value]      
[--passphrase value] [WORD]...                                           

Info: Convert a mnemonic seed (Electrum) to its numeric representation.  

Options (named):

-c [--config]        The path to the configuration settings file.        
-h [--help]          Get a description and instructions for this command.
-l [--language]      The language identifier of the dictionary of the    
                     mnemonic. Options are 'en', 'es', 'ja', 'pt',       
                     'zh_Hans' and 'any', defaults to 'any'.             
-p [--passphrase]    An optional passphrase for converting the mnemonic  
                     to a seed.                                          

Arguments (positional):

WORD                 The set of words that that make up the mnemonic. If 
                     not specified the words are read from STDIN.
```

### Example 1

TODO