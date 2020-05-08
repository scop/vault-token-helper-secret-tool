# vault-token-helper-secret-tool [![Tests](https://github.com/scop/vault-token-helper-secret-tool/workflows/Tests/badge.svg)](https://github.com/scop/vault-token-helper-secret-tool/actions?query=workflow%3ATests)

A [HashiCorp Vault](https://www.vaultproject.io/) token helper in a
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

## License

SPDX-License-Identifier: Apache-2.0
