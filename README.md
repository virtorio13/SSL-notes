### SSL-notes

# Convert Cert to PFX

```
set path=%path%;c:\openssl\bin
openssl pkcs12 -export -out "certificate_combined.pfx" -inkey "private.key" -in "certificate.crt" -certfile ca_bundle.crt
```

## Windows

# Bind installed SSL cert to port

```
netsh http add sslcert ipport=0.0.0.0:<port> certhash=<cert fingerprint> appid={<any guid>}
netsh http update sslcert ipport=0.0.0.0:<port> certhash=<cert fingerprint> appid={<any guid>}
```
