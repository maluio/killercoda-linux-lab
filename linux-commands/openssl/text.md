# OpenSSL

## Private key

* Generate a private key with des3 encryption with a length of 4096
* View the content of that key

## CSR (Certificate Signing Request)

* Generate a CSR
* View content of the CSR

Read the certs, the keys

##  CA certificate

* Generate a CA
* View the content of the CA


## Signed Certificate

* Create a server or client certificate using the key, CSR and CA certificate which you have created in this tutorial.
* View the content of the certificate

<br>

### Solutions

[Source](https://www.golinuxcloud.com/openssl-view-certificate/)

<details><summary>Solution: Private key</summary>

```shell
# Generate private key
openssl genrsa -des3 -out ca.key 4096

# View content
openssl rsa -noout -text -in ca.key
```

</details>

<details><summary>Solution: CSR</summary>

```shell
# Generate CSR
openssl req -new -key ca.key -out client.csr

# View content
openssl req -noout -text -in client.csr
```

</details>

<details><summary>Solution: CA cert</summary>

```shell
# Generate a CA cert
openssl req -new -x509 -days 365 -key ca.key -out ca.cert.pem

# View content
openssl x509 -noout -text -in ca.cert.pem
```
</details>

<details><summary>Solution: Signed Cert</summary>

```shell
# Generate a signed certificate
~]# openssl x509 -req -days 365 -in client.csr -CA ca.cert.pem -CAkey ca.key -CAcreateserial -out server.crt

# View content
 openssl x509 -noout -text -in server.crt
 ```
</details>
