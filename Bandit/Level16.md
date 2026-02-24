# Bandit Level 15 -> Level 16

## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL/TLS encryption.

Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.
### Datos de acceso
user: bandit14
password: 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo 
address: bandit.labs.overthewire.org
port: 2220

### Teoria


OpenSSL is a library for secure communication over networks. It implements the Transport Layer Security (TLS) and Secure Sockets Layer (SSL) cryptographic protocols that are, for example, used in HTTPS to secure the web traffic.

openssl s_client is the implementation of a simple client that connects to a server using SSL/TLS.
### Solución
<pre>
bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = SnakeOil
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = SnakeOil
verify return:1
---
Certificate chain
 0 s:CN = SnakeOil
   i:CN = SnakeOil
   a:PKEY: rsaEncryption, 4096 (bit); sigalg: RSA-SHA256
   v:NotBefore: Jun 10 03:59:50 2024 GMT; NotAfter: Jun  8 03:59:50 2034 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIFBzCCAu+gAwIBAgIUBLz7DBxA0IfojaL/WaJzE6Sbz7cwDQYJKoZIhvcNAQEL
BQAwEzERMA8GA1UEAwwIU25ha2VPaWwwHhcNMjQwNjEwMDM1OTUwWhcNMzQwNjA4
MDM1OTUwWjATMREwDwYDVQQDDAhTbmFrZU9pbDCCAiIwDQYJKoZIhvcNAQEBBQAD
ggIPADCCAgoCggIBANI+P5QXm9Bj21FIPsQqbqZRb5XmSZZJYaam7EIJ16Fxedf+
jXAv4d/FVqiEM4BuSNsNMeBMx2Gq0lAfN33h+RMTjRoMb8yBsZsC063MLfXCk4p+
09gtGP7BS6Iy5XdmfY/fPHvA3JDEScdlDDmd6Lsbdwhv93Q8M6POVO9sv4HuS4t/
jEjr+NhE+Bjr/wDbyg7GL71BP1WPZpQnRE4OzoSrt5+bZVLvODWUFwinB0fLaGRk
GmI0r5EUOUd7HpYyoIQbiNlePGfPpHRKnmdXTTEZEoxeWWAaM1VhPGqfrB/Pnca+
vAJX7iBOb3kHinmfVOScsG/YAUR94wSELeY+UlEWJaELVUntrJ5HeRDiTChiVQ++
wnnjNbepaW6shopybUF3XXfhIb4NvwLWpvoKFXVtcVjlOujF0snVvpE+MRT0wacy
tHtjZs7Ao7GYxDz6H8AdBLKJW67uQon37a4MI260ADFMS+2vEAbNSFP+f6ii5mrB
18cY64ZaF6oU8bjGK7BArDx56bRc3WFyuBIGWAFHEuB948BcshXY7baf5jjzPmgz
mq1zdRthQB31MOM2ii6vuTkheAvKfFf+llH4M9SnES4NSF2hj9NnHga9V08wfhYc
x0W6qu+S8HUdVF+V23yTvUNgz4Q+UoGs4sHSDEsIBFqNvInnpUmtNgcR2L5PAgMB
AAGjUzBRMB0GA1UdDgQWBBTPo8kfze4P9EgxNuyk7+xDGFtAYzAfBgNVHSMEGDAW
gBTPo8kfze4P9EgxNuyk7+xDGFtAYzAPBgNVHRMBAf8EBTADAQH/MA0GCSqGSIb3
DQEBCwUAA4ICAQAKHomtmcGqyiLnhziLe97Mq2+Sul5QgYVwfx/KYOXxv2T8ZmcR
Ae9XFhZT4jsAOUDK1OXx9aZgDGJHJLNEVTe9zWv1ONFfNxEBxQgP7hhmDBWdtj6d
taqEW/Jp06X+08BtnYK9NZsvDg2YRcvOHConeMjwvEL7tQK0m+GVyQfLYg6jnrhx
egH+abucTKxabFcWSE+Vk0uJYMqcbXvB4WNKz9vj4V5Hn7/DN4xIjFko+nREw6Oa
/AUFjNnO/FPjap+d68H1LdzMH3PSs+yjGid+6Zx9FCnt9qZydW13Miqg3nDnODXw
+Z682mQFjVlGPCA5ZOQbyMKY4tNazG2n8qy2famQT3+jF8Lb6a4NGbnpeWnLMkIu
jWLWIkA9MlbdNXuajiPNVyYIK9gdoBzbfaKwoOfSsLxEqlf8rio1GGcEV5Hlz5S2
txwI0xdW9MWeGWoiLbZSbRJH4TIBFFtoBG0LoEJi0C+UPwS8CDngJB4TyrZqEld3
rH87W+Et1t/Nepoc/Eoaux9PFp5VPXP+qwQGmhir/hv7OsgBhrkYuhkjxZ8+1uk7
tUWC/XM0mpLoxsq6vVl3AJaJe1ivdA9xLytsuG4iv02Juc593HXYR8yOpow0Eq2T
U5EyeuFg5RXYwAPi7ykw1PW7zAPL4MlonEVz+QXOSx6eyhimp1VZC11SCg==
-----END CERTIFICATE-----
subject=CN = SnakeOil
issuer=CN = SnakeOil
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 2103 bytes and written 373 bytes
Verification error: self-signed certificate
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 4096 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 18 (self-signed certificate)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 4FC59C973169AADAE2C23442719C9C709E25220ACAEA25A9AE393A09E362323B
    Session-ID-ctx: 
    Resumption PSK: 2E9B98F85A5F83BF24508519A25B2DA6DD9D3265365B93D002F5AC6683F77E17B09C358BD4DE2E87A6AF8786211A4F63
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 300 (seconds)
    TLS session ticket:
    0000 - ca 05 30 7c 7c 2e 15 ba-cf 68 d6 86 43 76 ac 94   ..0||....h..Cv..
    0010 - a7 77 78 fb 31 4d ee 16-d3 d8 39 b8 07 a6 1f 6d   .wx.1M....9....m
    0020 - 44 8a 3a 99 29 24 fe a6-22 58 a6 79 f3 cb c1 01   D.:.)$.."X.y....
    0030 - b4 60 97 93 87 3e 8e 7b-fa 12 e7 be 4e 80 61 bf   .`...>.{....N.a.
    0040 - dc bc d4 28 b5 34 dd 37-ac e0 1e cc 71 5e 4b cd   ...(.4.7....q^K.
    0050 - dd ee 51 f6 f8 df 35 a2-cf a5 2b 60 3d 3a d3 8e   ..Q...5...+`=:..
    0060 - 67 d2 f6 44 c6 2a 50 ff-0a b0 8f ce e8 e0 50 c0   g..D.*P.......P.
    0070 - 04 63 0a a0 93 50 ae a8-d6 ac 05 ab 25 88 43 d1   .c...P......%.C.
    0080 - 1f 24 10 64 18 4d eb 3c-5e ea be 11 73 52 b1 cf   .$.d.M.<^...sR..
    0090 - f4 e4 45 c9 0e f7 3f 8a-15 c9 ac b1 5e 3e c7 3a   ..E...?.....^>.:
    00a0 - 3a 84 ca 97 08 20 58 c8-31 aa 96 05 b5 aa 68 91   :.... X.1.....h.
    00b0 - 6a 1d 14 3b a2 81 9d 31-1a bf 33 8c ae 46 b8 89   j..;...1..3..F..
    00c0 - b3 6f 1d 06 f3 20 ed 54-0f 50 6b 96 78 e5 3a 25   .o... .T.Pk.x.:%
    00d0 - c5 eb ec 36 15 98 1d 88-4c 2a bf 71 60 7a 8b 87   ...6....L*.q`z..

    Start Time: 1771884749
    Timeout   : 7200 (sec)
    Verify return code: 18 (self-signed certificate)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 96CA6BD2FD074F8AD9EA61661A076EA3FAB1F0E08437D509AFF15CEC850B58FE
    Session-ID-ctx: 
    Resumption PSK: 4C41A2E3AE6A6DCEA3A447F67BFD974D66AA511DAFEB98703F5FB377BD189D6461CA8B071560AF447605D17CCB6661ED
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 300 (seconds)
    TLS session ticket:
    0000 - ca 05 30 7c 7c 2e 15 ba-cf 68 d6 86 43 76 ac 94   ..0||....h..Cv..
    0010 - 76 fa 48 13 f9 30 57 10-4b ec 53 50 a6 3d f8 93   v.H..0W.K.SP.=..
    0020 - ac 20 f9 c7 bf 8a 6f 92-85 2a ed 86 cc 97 c3 ac   . ....o..*......
    0030 - 76 bb 0e ea 06 a0 50 b2-ba 3d f8 b7 e2 7c f0 c7   v.....P..=...|..
    0040 - 64 c6 43 bd 15 70 84 49-fb 3c cd fb a4 66 3f 7e   d.C..p.I.<...f?~
    0050 - ac d1 06 7a c3 9e e7 0b-3a b1 f3 f0 67 54 7b aa   ...z....:...gT{.
    0060 - d7 99 08 95 b0 04 5f ed-55 a6 21 bd aa 54 79 a2   ......_.U.!..Ty.
    0070 - 2c 6f 74 1f 5f 62 05 3b-54 13 4a 41 56 37 da 82   ,ot._b.;T.JAV7..
    0080 - 60 a6 70 f4 d3 a2 68 8c-fa 09 49 d8 ca 79 39 96   `.p...h...I..y9.
    0090 - ff 73 c7 fd 72 f9 a1 2c-16 ea ee dc da aa b7 7e   .s..r..,.......~
    00a0 - 70 e8 0c e4 bb fe 92 16-fd a7 16 7e 87 28 31 79   p..........~.(1y
    00b0 - 10 76 bc f3 6a 8f ad dd-63 e8 0c 98 26 c0 9e b3   .v..j...c...&...
    00c0 - c9 9e 54 ca c8 c3 43 5f-94 78 27 1a 96 b8 9d d9   ..T...C_.x'.....
    00d0 - cf 75 e6 11 8f cc 55 09-a8 d9 8d da c6 25 61 15   .u....U......%a.

    Start Time: 1771884749
    Timeout   : 7200 (sec)
    Verify return code: 18 (self-signed certificate)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
Correct!
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx

closed
bandit15@bandit:~$ 


<pre>


**Flag: kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx**