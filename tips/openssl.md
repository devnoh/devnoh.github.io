# OPENSSL

## How to convert a certificate into the appropriate format

### Convert x509 to PEM
```
$ openssl x509 -in certificatename.cer -outform PEM -out certificatename.pem
```

### Convert PEM to DER
```
$ openssl x509 -outform der -in certificatename.pem -out certificatename.der
```

### Convert DER to PEM
```
$ openssl x509 -inform der -in certificatename.der -out certificatename.pem
```

### Convert PFX to PEM
```
$ openssl pkcs12 -in certificatename.pfx -out certificatename.pem
```

### Convert CER and Private Key to PFX
```
$ openssl pkcs12 -export -in certificatename.cer -inkey privateKey.key -out certificatename.pfx -certfile  cacert.cer
```