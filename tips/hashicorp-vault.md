# HashCorp Vault


$ brew install vault
$ vault server --dev --dev-root-token-id="00000000-0000-0000-0000-000000000000"

```
WARNING! dev mode is enabled! In this mode, Vault runs entirely in-memory
and starts unsealed with a single unseal key. The root token is already
authenticated to the CLI, so you can immediately begin using Vault.

You may need to set the following environment variable:

    $ export VAULT_ADDR='http://127.0.0.1:8200'

The unseal key and root token are displayed below in case you want to
seal/unseal the Vault or re-authenticate.

Unseal Key: MFSqWBZx4tmBKc5bwmBVCiiPvieaFEkMp2ZITFjuP2k=
Root Token: 00000000-0000-0000-0000-000000000000

Development mode should NOT be used in production installations!
```

$ export export VAULT_TOKEN="00000000-0000-0000-0000-000000000000"
$ export VAULT_ADDR="http://127.0.0.1:8200"

$ vault write secret/github github.oauth2.key=foobar
