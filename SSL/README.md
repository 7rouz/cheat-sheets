# configuring SSL connection 

## fusion certificate and key into one PEM/P12 file

``` openssl pkcs12 -export -out certif.p12 -inkey certificate.key -in certificate.crt ```

## get certificate from PEM/P12 file

``` openssl pkcs12 -in certificate.p12 -clcerts -nokeys -out certificate.crt ```

## get key from PEM/P12 file

``` openssl pkcs12 -in certificate.p12 -nocerts -out certificate.key ```

## encrypt a file into Base64 

``` cat file_to_encrypt | base64 -w 0 > encypted_output_file```

## decrypt Base64 encrypted file

``` cat encrypted_file | base64 -d > decrypted_output_file```

## check if the key is password protected

If the key is password protected, you will see a "password:" prompt.

The flags in this command are:

-y Read private key file and print public key.

-f Filename of the key file.

``` ssh-keygen -y -f certificate.key ```

## remove passphrase of a private key 

``` openssl rsa -passin pass:PASSPHRASE -in passphrase_protected_key -out clear_key ```
