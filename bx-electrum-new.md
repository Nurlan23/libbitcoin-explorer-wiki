Create a mnemonic seed (Electrum) from entropy.

**WARNING**: mnemonic should be created from properly generated entropy.

```sh
$ bx electrum-new --help
```
```
Usage: bx electrum-new [-h] [--config value] [--language value] [--prefix
value] [SEED]                                                            

Info: Create a mnemonic seed (Electrum) from entropy. WARNING: mnemonic  
should be created from properly generated entropy.                       

Options (named):

-c [--config]        The path to the configuration settings file.        
-h [--help]          Get a description and instructions for this command.
-l [--language]      The language identifier of the mnemonic dictionary  
                     to use. Options are 'en', 'es', 'pt', 'ja',         
                     'zh_Hans' and 'any', defaults to 'en'.              
-p [--prefix]        The electrum seed type identifier to use. Options   
                     are 'standard', 'witness', and 'dual' (for two      
                     factor authentication), defaults to 'standard'.     

Arguments (positional):

SEED                 The Base16 entropy from which the mnemonic is       
                     created. If not specified the entropy is read from  
                     STDIN.
```

### Example 1

```
$ echo "05e669b4270f4e25bce6fc3736170d423c" | bx electrum-new
giggle crush argue inflict wear defy combine evolve tiger spatial crumble fury
```

### Example 2

```
$ bx seed -b 136 | bx electrum-new
fatigue mind comfort web follow wonder vibrant pear guide key seed cup abuse
```