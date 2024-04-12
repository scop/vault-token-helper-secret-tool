# vault-token-helper-secret-tool [![pre-commit.ci status](https://results.pre-commit.ci/badge/github/scop/vault-token-helper-secret-tool/main.svg)](https://results.pre-commit.ci/latest/github/scop/vault-token-helper-secret-tool/main)

A [HashiCorp Vault](https://www.vaultproject.io/) [token helper](https://www.vaultproject.io/docs/commands/token-helper) in a
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

When changing between tokens, the helper name needs to be swapped in
Vault config accordingly though. Or alternatively, multiple config
files (with uniquely named helper in each of them) can be used too,
and the `VAULT_CONFIG_PATH` environment variable changed as needed to
choose between them.

## Alternatives, credits

Inspired by
[joemiller/vault-token-helper](https://github.com/joemiller/vault-token-helper),
but much smaller and simpler. For something more elaborate than this
one, as well as for support for other store backends besides what
libsecret works with, that'd be one alternative to look into.

## License

SPDX-License-Identifier: Apache-2.0
