# OpenSSL

## Signed Certificate

* Create a server certificate `server.crt` using the key, CSR and CA certificate which you have created in this tutorial.
* View the content of the certificate

<br>

### Solutions

<details><summary>Solution: Signed Cert</summary>

```shell
# Generate a signed certificate
~]# openssl x509 -req -days 365 -in client.csr -CA ca.cert.pem -CAkey ca.key -CAcreateserial -out server.crt

# View content
 openssl x509 -noout -text -in server.crt
 ```
</details>
