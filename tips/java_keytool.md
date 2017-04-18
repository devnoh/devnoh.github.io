# JAVA KEYTOOL

## Export the certificate as a file

```
keytool -export -rfc -keystore keystore.jks -file public.cer
Enter keystore password:  

*****************  WARNING WARNING WARNING  *****************
* The integrity of the information stored in your keystore  *
* has NOT been verified!  In order to verify its integrity, *
* you must provide your keystore password.                  *
*****************  WARNING WARNING WARNING  *****************

Certificate stored in file <public.cer>
```

## Export the certificate as a string

```
$ keytool -export -rfc -keystore keystore.jks
Enter keystore password:  

*****************  WARNING WARNING WARNING  *****************
* The integrity of the information stored in your keystore  *
* has NOT been verified!  In order to verify its integrity, *
* you must provide your keystore password.                  *
*****************  WARNING WARNING WARNING  *****************

-----BEGIN CERTIFICATE-----
MIIDbzCCAlegAwIBAgIER6LWkzANBgkqhkiG9w0BAQsFADBoMQswCQYDVQQGEwJV
UzELMAkGA1UECBMCQ0ExDzANBgNVBAcTBklydmluZTEUMBIGA1UEChMLQXV0b0dy
YXZpdHkxEDAOBgNVBAsTB0JhY2tlbmQxEzARBgNVBAMTClNlaHdhbiBOb2gwHhcN
MTcwNDE3MjI0MjUyWhcNMTcwNzE2MjI0MjUyWjBoMQswCQYDVQQGEwJVUzELMAkG
A1UECBMCQ0ExDzANBgNVBAcTBklydmluZTEUMBIGA1UEChMLQXV0b0dyYXZpdHkx
EDAOBgNVBAsTB0JhY2tlbmQxEzARBgNVBAMTClNlaHdhbiBOb2gwggEiMA0GCSqG
SIb3DQEBAQUAA4IBDwAwggEKAoIBAQCbvpSXiFSfY9b1D6rrvOHAZY/qaYHmnoUn
TUgZKYJNAqejZbrPUKLa215tLQrc1wosj1jSY88rguT0AbL2TzpKe/vdCj3YHGj3
1mOPyBkIwjey12a6xgIF8KoPi2QUywud/hnL4Q+Z0GQKxUplFj6o0gjlqiz4NYCw
AJ7r3ruGEv2z/3Xfi9pwCCyM8uc7mXwr1Q6aAYQTpK4n1ax39TbRyDTfnD1sQCej
xe+2jLl/k5Q+7c43S7nlEdtXfhHryWde+7FzlJUqIEo7r7x4+1kWC8PLy7+lmEvd
bbxnO56qvgyfYwUboSuthAhiaoYYfFXFfKKIVY4HShpvXKCz2JAxAgMBAAGjITAf
MB0GA1UdDgQWBBQVl1Ld8eauV/KMjM2y/mOoBhUKdDANBgkqhkiG9w0BAQsFAAOC
AQEAmLRmMfjXTux152l5qv40Ub6LQHGPAiIvHTmEcvuMzuzs3Zx/0Q+uAKbwRzRa
XIPN9DAEw75i4u0bV4E395/Cgb+n50R9GndB0IYqYAcCWjsFaur3dKCxJL/vGHAt
gehv2WCnDZPpN1gl7ZlQECTTfJ21FMkffXicYhT5TXocLl5mZ+3DB6nK4gPCjtHS
tPP7DtZcE/V/aCwj/jiFwcRniAQduZ86HJyqG56LGAKIfdPtdkx7qfQD8NV3lQcE
r0df1c8mUkuZsXadBjoPyBevdRintm2Qc32wjHT33977zqZQNghd/t5TLuciAXvr
6gUFiHLyzFVjfRDgAFsaJmprKg==
-----END CERTIFICATE-----
```

## Print the certificate n human-readable form

```
$ keytool -printcert -file public.cer
Owner: CN=Sehwan Noh, OU=Backend, O=AutoGravity, L=Irvine, ST=CA, C=US
Issuer: CN=Sehwan Noh, OU=Backend, O=AutoGravity, L=Irvine, ST=CA, C=US
Serial number: 47a2d693
Valid from: Mon Apr 17 15:42:52 PDT 2017 until: Sun Jul 16 15:42:52 PDT 2017
Certificate fingerprints:
         MD5:  25:99:6F:5A:0F:C1:5C:7A:C5:4B:35:1F:19:17:2B:9F
         SHA1: B5:F8:88:3D:EF:D8:8C:9B:44:3D:03:F7:E6:BA:B9:39:52:13:E5:0A
         SHA256: 8F:0F:F0:54:9C:D2:30:DB:68:96:EF:AF:D5:FE:2C:7F:51:3E:F6:6A:3A:77:D6:AA:E0:43:04:F1:3F:F2:19:4C
         Signature algorithm name: SHA256withRSA
         Version: 3

Extensions: 

#1: ObjectId: 2.5.29.14 Criticality=false
SubjectKeyIdentifier [
KeyIdentifier [
0000: 15 97 52 DD F1 E6 AE 57   F2 8C 8C CD B2 FE 63 A8  ..R....W......c.
0010: 06 15 0A 74                                        ...t
]
]
```