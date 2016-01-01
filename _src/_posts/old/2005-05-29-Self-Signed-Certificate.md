---
redirect_from:
  /blog/2005/05/how-to-create-self-signed-certificate.html
---
How to create a self-signed certificate with openssl for testing use or for setting up something like stunnel:

    openssl req -new -x509 -keyout cakey.pem -out cacert.pem -days 3650

'req' with '-new' tells it to create a new certificate, and '-x509' tells it that it should be self-signed. The file after '-keyout' contains the private key, and the file after '-out' contains the public key. The '-days' option specifies how long this certificate is valid. 
The key will be created encrypted with a password that you put in at the prompt. In order to install this certificate on you server, it will first need to be decrypted, which you can do like this:

openssl rsa -in cakey.pem -out cakey-unencrypted.pem
