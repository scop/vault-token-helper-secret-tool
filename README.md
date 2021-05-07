# vault-token-helper-secret-tool [![Tests](https://github.com/scop/vault-token-helper-secret-tool/workflows/Tests/badge.svg)](https://github.com/scop/vault-token-helper-secret-tool/actions?query=workflow%3ATests)

A [HashiCorp Vault](https://www.vaultproject.io/) [token
helper](https://www.vaultproject.io/docs/commands/token-helper) in a
few lines of POSIX shell code, using
[libsecret's](https://wiki.gnome.org/Projects/Libsecret)
`secret-tool`.

## Usage

Clone this repo or install the script somewhere some other way, run it
with the `enable` argument:

```shell
./vault-token-helper-secret-tool enable
```

### Advanced

Multiple different tokens can be used with this helper by installing
(e.g. by symlinking) it to another name; the part after
`vault-token-helper-secret-tool` in its basename will be used to
identify tokens managed by that helper in the secret store. The
default identifier for a suffixless script is `default`.

You'll need to swap the helper name in your Vault config though when
changing context, or use multiple configs (with uniquely named helper
in each of them) and use the `VAULT_CONFIG_PATH` to choose between
them.

## Alternatives, credits

Inspired by
[joemiller/vault-token-helper](https://github.com/joemiller/vault-token-helper),
but much smaller and simpler. For something more elaborate than this
one, as well as for support for other store backends besides what
libsecret works with, that'd be one alternative to look into.

## License

SPDX-License-Identifier: Apache-2.0
