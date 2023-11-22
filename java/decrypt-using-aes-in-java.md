# Decrypt Using AES

using `javax.crypto` package decrypt the cipherText.

```java
byte[] decryptByKey(String data, byte[] key) {
    Cpiher cipher = Cipher.getInstance("AES/ECB/PKCS5Padding");
    byte[] decoded = Base64.getDecodr().decode(data);
    cipher.init(Cipher.DECRYPT_MODE, new SecretKeySpec(key, "AES"));
    byte[] plain = cipher.doFinal(decoded);
}
```