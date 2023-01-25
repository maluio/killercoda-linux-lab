# OpenSSL

## Private key

* Generate a private key `ca.key` with a length of 4096
* View the content of that key

### Solutions

[Source](https://www.golinuxcloud.com/openssl-view-certificate/)

<details><summary>Solution: Private key</summary>

```shell
# Generate private key
openssl genrsa -out ca.key 4096

# View content
openssl rsa -noout -text -in ca.key
```

</details>
