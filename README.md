# openSSLGeneration

# Generate the Open SSL Certificate and import in KeyStore

## Please follow the steps mention below.

#### Step 1 openssl req -new -newkey rsa:2048 -nodes -keyout https://sourabhlodha.com.key -out sourabhlodha.com.csr -config sourabhlodha.com.cfg

#### Step 2 openssl pkcs12 -export -in sourabhlodha.com.crt -inkey sourabhlodha.com.key -out keystore.p12 -name sourabhlodha.com
## (this imports the certificate with private key into a temporary p12 formar keystore)

#### Step 3  keytool -importkeystore -deststorepass PASSWORD -destkeypass PASSWORD -destkeystore keystore.jks -srckeystore keystore.p12 -srcstoretype PKCS12 -srcstorepass PASSWORD -alias sourabhlodha.com

## (this exports the certificate from p12 file into the java keystore.jks)

#### Step 4 VERIFY : keytool -v -list -keystore keystore.jks -storetype JKS
## (this verified if the cert was imported properly)
