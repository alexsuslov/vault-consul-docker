# Managing Secrets
## network web
```
docker network create web
```
## Consul

### Start consul
```
docker-compose up -d --build consul consul-worker
```
### Secret id

```
docker-compose exec consul consul acl bootstrap
...
AccessorID:       XXXXXXX
SecretID:         XXXXXXX
...
```

### Policy for vault

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
```

```
# Vault

## Start vault
```
docker-compose u -d vault
```
## 



## Want to learn how to build this?

Check out the [post](https://testdriven.io/managing-secrets-with-vault-and-consul).

## Want to use this project?

1. Fork/Clone

1. Build the images and run the containers:

    ```sh
    $ docker-compose up -d --build
    ```

1. You can now interact with both Vault and Consul. View the UIs at [http://localhost:8200/ui](http://localhost:8200/ui) and [http://localhost:8500/ui](http://localhost:8500/ui).


