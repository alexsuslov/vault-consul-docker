# Managing Secrets
## Consul

Start consul
```
docker-compose up -d --build consul consul-worker
```
create secret id

docker-compose exec consul consul acl bootstrap

```
AccessorID:       cb86e406-553b-8c65-3de0-e30f1a90a4e1
SecretID:         c1b1143b-744e-cab2-5f04-d9f514a5fc43
Description:      Bootstrap Token (Global Management)
Local:            false
Create Time:      2019-12-23 14:29:11.868595878 +0000 UTC
Policies:
   00000000-0000-0000-0000-000000000001 - global-management
```

### Create policy for vault

From https://www.vaultproject.io/docs/configuration/storage/consul.html#ACLs

name: vault
```
{
  "key_prefix": {
    "vault/": {
      "policy": "write"
    }
  },
  "node_prefix": {
    "": {
      "policy": "write"
    }
  },
  "service": {
    "vault": {
      "policy": "write"
    }
  },
  "agent_prefix": {
    "": {
      "policy": "write"
    }

  },
  "session_prefix": {
    "": {
      "policy": "write"
    }
  }
}
```

### create token

### add token to vault config



# Vault



## Want to learn how to build this?

Check out the [post](https://testdriven.io/managing-secrets-with-vault-and-consul).

## Want to use this project?

1. Fork/Clone

1. Build the images and run the containers:

    ```sh
    $ docker-compose up -d --build
    ```

1. You can now interact with both Vault and Consul. View the UIs at [http://localhost:8200/ui](http://localhost:8200/ui) and [http://localhost:8500/ui](http://localhost:8500/ui).


