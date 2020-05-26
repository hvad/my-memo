# Openssl

## Création

### Générer une clé privée

    # openssl genrsa -out key.pem 2048

### Générer un CSR à partir d’une clé existante

    # openssl req -out csr.csr -key key.pem -new

### Générer une nouvelle clé et un CSR

    # openssl req -out csr.csr -new -newkey rsa:2048 -nodes -keyout key.pem

### Générer un certificat auto-signé valide 365 jours

    # openssl req -x509 -sha256 -nodes -newkey rsa:2048 -keyout key.pem -out certificate.crt -days 365

### Générer un CSR sur la base d’un certificat et d’une clé existants

    # openssl x509 -x509toreq -in certificate.crt -signkey key.pem -out csr.csr

### Retirer la pass-phrase d’une clé privée

    # openssl rsa -in key.pem -out newkey.pem

## Informations sur un certificat

### Obtenir la date d’expiration

    # openssl x509 -noout -in certificate.crt -dates

### Obtenir le signataire d’un certificat

    # openssl x509 -noout -in certificate.crt  -issuer

## Vérification des certificats

### Vérifier qu’une clé privée et un CSR correspondent

    # openssl rsa -noout -modulus -in key.pem | openssl md5
    # openssl req -noout -modulus -in csr.txt | openssl md5

### Vérifier qu’une clé privée et un certificat correspondent

    # openssl x509 -noout -modulus -in cert.crt | openssl md5
    # openssl rsa -noout -modulus -in key.pem | openssl md5

### Vérifier un CSR

    # openssl req -text -noout -verify -in csr.csr

### Vérifier une clé privée

    # openssl rsa -in key.pem -check

### Vérifier un certificat

    # openssl x509 -in certificate.crt -text -noout

### Vérifier un certificat PKCS12

    # openssl pkcs12 -info -in store.p12

## Tester une connexion à un serveur

### Vérifier une connexion et la chaîne de confiance sur un port TCP

    # openssl s_client -connect host:443

### Vérifier la prise en charge de SSLv2, SSLv3, TLS1.0, TLS1.1 et TLS1.2

    # openssl s_client -connect host:443 -ssl2
    # openssl s_client -connect host:443 –ssl3
    # openssl s_client -connect host:443 –tls1
    # openssl s_client -connect host:443 –tls1_1
    # openssl s_client -connect host:443 –tls1_2

### Vérifier la prise en charge d’un algorithme de chiffrement sur un serveur (openssl ciphers)

    # openssl s_client -cipher 'ECDHE-ECDSA-AES256-SHA' -connect host:443

## Conversions

### Convertir un PEM en DER

    # openssl x509 -outform der -in certificate.crt -out certificate.der

### Convertir un DER en PEM

    # openssl x509 -inform der -in certificate.der -out certificate.pem

### Conversion PEM en PKCS12

    # openssl pkcs12 -export -inkey  key.pem -in certificate.crt -name SuperCertificat -out store.p12

### Conversion PKCS12 en PEM

    # openssl pkcs12 -in store.p12 -out store.pem -nodes
