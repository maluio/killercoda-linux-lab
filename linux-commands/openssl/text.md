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

### Solution

[Source](https://www.golinuxcloud.com/openssl-view-certificate/)

```plain
# Generate private key
openssl genrsa -des3 -out ca.key 4096

# View content
openssl rsa -noout -text -in ca.key

```{{exec}}

```plain
# Generate CSR
openssl req -new -key ca.key -out client.csr

# View content
openssl req -noout -text -in client.csr
```{{exec}}

```plain
# Generate a CA cert
openssl req -new -x509 -days 365 -key ca.key -out ca.cert.pem

# View content
openssl x509 -noout -text -in ca.cert.pem
```{{exec}}

```plain
# Generate a signed certificate
~]# openssl x509 -req -days 365 -in client.csr -CA ca.cert.pem -CAkey ca.key -CAcreateserial -out server.crt

# View content
 openssl x509 -noout -text -in server.crt
 ```{{exec}}
