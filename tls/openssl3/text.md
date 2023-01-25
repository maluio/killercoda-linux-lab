# OpenSSL

##  CA certificate

* Generate a CA `ca.cert.pem`
* View the content of the CA

### Solutions

<details><summary>Solution: CA cert</summary>

```shell
# Generate a CA cert
openssl req -new -x509 -days 365 -key ca.key -out ca.cert.pem

# View content
openssl x509 -noout -text -in ca.cert.pem
```
</details>
