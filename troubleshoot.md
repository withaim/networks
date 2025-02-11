# Troubleshooting

- [Troubleshooting](#troubleshooting)
  - [Celestia-app](#celestia-app)
    - [Validator Node setup](#validator-node-setup)

## Celestia-app

### Validator Node setup
If you get an error such as 

```Error: <keyname>: key not found```,

this means your key, the field referenced by the `--from` option, does not exist.

> Note: By default, the script for creating a key is utilizing `test` backend. Please, use the flag `--keyring-backend` if you opt for a different key-type.

You can fix this by adding your key manually to the keyring via:

```sh
celestia-appd keys add --recover <keyname>
# or 
celestia-appd keys add --recover <keyname> --keyring-backend <other_format>
``` 

followed by a prompt to enter a bip39 mnemonic, which is the mnemonic that was created as part of `1_create_key.sh` script in the first step.

You'll also be asked for a passphrase which is an input you have to define.