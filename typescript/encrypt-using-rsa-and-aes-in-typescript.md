# Encrypt Using RSA And AES In TypeScript

- RSA

import `jsencrypt` package

```shell
npm install jsencrypt 
```

encrypt plainText by publicKey

```typescript
export function Encrypt() {
    let jsencrypt = new JSEncrypt()

    let publicKey = `-----BEGIN PUBLIC KEY-----\n${publicKeyContent}\n-----END PUBLIC KEY-----`;
    jsencrypt.setPublicKey(publicKey)

    let data = "test encrypt in rsa"
    let cipher = jsencrypt.encrypt(data)
    return cipher
}
```

- AES

import `crypto-js` package

```shell
npm install crypto-js
```

encrypt plainText using aes

```typescript
export function Encrypt() {
    const AES_OPT = {
        mode: CryptoJS.mode.ECB,
        padding: CryptoJS.pad.Pkcs7,
    }
    let key = "128-bit KEY";
    key = CryptoJS.enc.Utf8.parse(key);

    let data = "test encrypt in aes"
    let cipher = CryptoJS.AES.encrypt(data, key, AES_OPT)

    return cipher
}
```