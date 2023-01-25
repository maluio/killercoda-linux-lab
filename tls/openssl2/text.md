# OpenSSL

## CSR (Certificate Signing Request)

* Generate a CSR `client.csr`
* View content of the CSR

<br>

### Solutions

<details><summary>Solution: CSR</summary>

```shell
# Generate CSR
openssl req -new -key ca.key -out client.csr

# View content
openssl req -noout -text -in client.csr
```

</details>
