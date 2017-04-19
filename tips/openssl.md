# OPENSSL

## X.509 Certificate

### Encodings (also used as file extensions)

* **DER** is the method of encoding the data that makes up the certificate. DER itself could represent any kind of data, but usually it describes an encoded certificate or a CMS container. The structure of a certificate is described using the ASN.1 data representation language. BER and DER are binary encoding methods for data described by ASN.1.

* **PEM** is a method of encoding binary data as a string (ASCII armored data prefixed with a "-----BEGIN ..." line). It contains a header and a footer line (specifying the type of data that is encoded and showing begin/end if the data is chained together) and the data in the middle is the base 64 data. In the case that it encodes a certificate it would simply contain the base 64 encoding of the DER certificate. PEM stands for Privacy Enhanced Mail; mail cannot contain unencoded binary values such as DER.

### Common File Extensions

* **.CER**  The CER extension is used for certificates. It is normally DER encoded data, but Windows may also accept PEM encoded data. You need to take a look at the content (e.g. using the file utility on posix systems) to see what is within the file to be 100% sure.

* **.CRT** The CER and CRT extensions are nearly synonymous. It is encoded as ASCII PEM (Base 64).


* **.KEY** The KEY extension is used both for public and private PKCS#8 keys. The keys may be encoded as binary DER or as ASCII PEM.

## Generate SSL Certificates

### Generate a Self-signed Certificate
```
$ openssl req -x509 -newkey rsa:2048 -keyout domain.key -out domain.crt -days 365 -nodes
```

Options:
```
req
PKCS#10 certificate request and certificate generating utility.

-x509
this option outputs a self signed certificate instead of a certificate request. This is typically used to generate a test certificate or a self signed root CA.

-newkey arg
this option creates a new certificate request and a new private key. The argument takes one of several forms. rsa:nbits, where nbits is the number of bits, generates an RSA key nbits in size.

-keyout filename
this gives the filename to write the newly created private key to.

-out filename
This specifies the output filename to write to or standard output by default.

-days n
when the -x509 option is being used this specifies the number of days to certify the certificate for. The default is 30 days.

-nodes
if this option is specified then if a private key is created it will not be encrypted.
```

### Generate a Self-signed Certificate with an Existing Private Key
```
openssl req -x509 -new -key domain.key -out domain.crt -days 365
```       

## View Certificates

### View PEM Encoded Certificate
```
$ openssl x509 -in domain.pem -text -noout
$ openssl x509 -in domain.cer -text -noout
$ openssl x509 -in domain.crt -text -noout
```

### View DER Encoded Certificate
```
$ openssl x509 -in domain.der -inform der -text -noout
$ openssl x509 -in domain.cer -inform der -text -noout
```

## Convert Certificate Formats

### Convert x509 to PEM
```
$ openssl x509 -in domain.cer -outform PEM -out domain.pem
```

### Convert PEM to DER
```
$ openssl x509 -outform der -in domain.pem -out domain.der
```

### Convert DER to PEM
```
$ openssl x509 -inform der -in domain.der -out domain.pem
```

### Convert PFX to PEM
```
$ openssl pkcs12 -in domain.pfx -out domain.pem
```

### Convert CER and Private Key to PFX (PKCS#12)
```
$ openssl pkcs12 -export -in domain.cer -inkey private.key -out domain.pfx -certfile cacert.cer
```

## Private Keys

### Create a Private Key
```
$ openssl genrsa -des3 -out domain.key 2048
```

## Verify a Private Key
```
$ openssl rsa -check -in domain.key
```

### Verify a Private Key Matches a Certificate and CSR
```
$ openssl rsa -noout -modulus -in domain.key | openssl md5
$ openssl x509 -noout -modulus -in domain.crt | openssl md5
$ openssl req -noout -modulus -in domain.csr | openssl md5
```

### Encrypt a Private Key
```
$ openssl rsa -des3 -in unencrypted.key -out encrypted.key
```

### Decrypt a Private Key
```
$ openssl rsa -in encrypted.key -out decrypted.key
```

### Convert PEM to DER
```
$ openssl rsa -outform der -in domain.pem -out domain.der
```

### Convert DER to PEM
```
$ openssl rsa -inform der -in domain.der -out domain.pem
```

## To remove the Bag Attributes (i.e the header part of a cert.pem) 
```
$ openssl x509 -in domain.crt -out domain.crt
$ openssl rsa -in domain.key -out domain.key
```

## References
* https://www.digitalocean.com/community/tutorials/openssl-essentials-working-with-ssl-certificates-private-keys-and-csrs
