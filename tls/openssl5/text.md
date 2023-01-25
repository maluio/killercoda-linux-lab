# OpenSSL

## View remote cert

View the cert from *redhat.com*

### Solutions

<details><summary>Solution</summary>

```shell
openssl s_client -connect redhat.com:443  | openssl x509 -text -noout
```

</details>