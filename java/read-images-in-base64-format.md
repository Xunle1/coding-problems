# Read Images In Base64 Format

use `javax.imageio` and `java.awt.image` package to read images in base64 format.

```java
import javax.imageio.ImageIO;
import java.awt.image.BufferdImage;
import java.io.*;
import java.util.Base64;

public void readImage(String data) throw Exception {
    byte[] bytes = Base64.getDecoder().decode(data);
    BufferdImage image = ImageIO.read(new ByteArrayInputStream(bytes));
    FileOutputStream fos = new FileOutputStream("test.png");
    ImageIO.write(image, "png", fos);
}
```