# Generate Keypair In CLI

Using JDK `keytool` generate keypair.

```shell
keytool -genkeypair -keyalg RSA -keysize 2048 -alias mykey -keystore keystore.jks
```

Then you can use command below to get public key.

```java
KeyStore keyStore = KeyStore.getInstance("JKS");
keyStore.load(new FileInputStream(PATH_TO_KEYSTORE), PASSWORD.toCharArray());
Certificate cert = keyStore.getCertificate("mykey");
PublicKey key = cert.getPublicKey();
```

Show public/private key in pem format.

```shell
keytool -list -rfc --keystore .\keystore.jks | openssl x509 -inform pem -pubkey
``