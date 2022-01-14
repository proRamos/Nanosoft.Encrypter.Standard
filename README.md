# Nanosoft.Encrypter.Standard
Encrypter
![NanosoftEncrypterBanner](https://user-images.githubusercontent.com/89319069/149569808-4aedb7f7-3ce2-4d2a-a131-03c1530d35e9.png)
## About this library
Nanosoft.Encrypter is a symmetric key that operates on 64-bit blocks of information and uses 128-bit keys.
Nanosoft.Encrypter generates a unique key by itself every time it is executed, excluding the supply of the same.
The algorithm used works differently, as it uses confusion and diffusion to encrypt the text. In practice, it uses four algebraic groups with mixed operations, and that's how Nanosoft.Encrypter manages to protect information.

## .NET Core 5 Standard
This library has been implemented for .NET Core Standard and newer.

## Test cases
This library contains test cases for the most important functions to ensure functionality.

## Citation
The library can also be cited in scientific works, for example as follows:

Dan Boneh, Stanford University (2021): Online Cryptography Course. Site: https://crypto.stanford.edu/~dabo/courses/OnlineCrypto/

## Example (1.0.0)
### Heads up!
This version was developed more specifically for password encryption, so it does not support Extended ASCII Codes.
See more at: https://www.asciitable.com/
```csharp
using System;
using Nanosoft.Encrypter;

namespace Nanosoft.Encrypter.ConsoleExample
{
    class Program
    {
        static void Main(string[] args)
        {
            var crypter = new LoadEncryption();
            string MyString             = "This string will be encrypted " +
                "| a b c d e f g h i j k l m n o p q r s t u v w x y z" +
                "| A B C D E F G H I J K L M N O P Q R S T U V W X Y Z" +
                "| 0 1 2 3 4 5 6 7 8 9 0 ? + ´ º ~ Ç , . @ £ § € { [ ] }";
            string MyEncryptedString    = crypter.GetEncryptedString(MyString);

            Console.WriteLine("\nString to be encrypted:\n");

            Console.WriteLine(MyString);

            Console.WriteLine("\nThe encrypted form:\n");

            Console.WriteLine(MyEncryptedString);

            Console.WriteLine("\nThe Decrypted form:\n");

            Console.WriteLine(crypter.GetDecryptedString(MyEncryptedString));
        }
    }
}

```
```console
String to be encrypted:

This string will be encrypted | a b c d e f g h i j k l m n o p q r s t u v w x y z| A B C D E F G H I J K L M N O P Q R S T U V W X Y Z| 0 1 2 3 4 5 6 7 8 9 0 ? + ´ º ~ Ç , . @ £ § ? { [ ] }

The encrypted form:

W1tbX19fX19fLV1dXVtbW19fX19fX19dXV1bW1tfX19fX18tXV1dW1tbX19fX19fX11dXVtbQCoqKipdXXwtLS0tKi0tKnwzLV8tM3wtLSoqKi0tfCB8LS0qKiotLXx8LS0qKioqfHwtLSoqLS0qfDMtXy0zfC0tKi0tKi0tfHwtLS0tKi0tLS18IHwqLS0tLS0tKnwzLV8tM3wtLSotLS0tLS18fC0tKi0tLS0tLXwgfC0tLS0tLS0tLS18My0tXzMgMy0tXzN8LS0qLS0qLS18fC0tLS0tLS0tKnx8LS0qKi0tKnx8Ki0tLS0qKnx8LS0qLS0qKnx8LS0qKioqfDMtLV8zfC0tLS0tLSotLXwgfCAzLS0tMyB8LS0tLS0tLS0tLXwgfC0tLS0tLS0tKnwgfC0tLS0tLSotLXwgMy0tXzMgfC0tLS0tLSoqfCB8LS0tLSotLS0tfCB8LS0tLSotLSp8IDMtXy0zIHwtLS0tKiotLXwgfC0tLS0qKip8IHwtLSotLS0tLS18IHwtLSotLS0tKnwgfC0tKi0tKi0tfCAzLV9fMyB8LS0qLS0qKnwgfC0tKiotLS0tfCB8LS0qKi0tKnwgfC0tKioqLS18IHwtLSoqKip8IDNfLS0zIHwqLS0tLS0tLS18IHwqLS0tLS0tKnwgfCotLS0tKi0tfCB8Ki0tLS0qKnwgfCotLSotLS0tfHwgW1s2LS0tNl1dIFtbQEBAQEBdXSBbW0BAQEAqXV0gW1tAQEAqQF1dIFtbNi0tXzZdXSBbW0BAQCoqXV0gW1tAQCpAQF1dIFtbQEAqQCpdXSBbWzYtXy02XV0gW1tAQCoqQF1dIFtbQEAqKipdXSBbW0AqQEBAXV0gW1tAKkBAKl1dIFtbQCpAKkBdXSBbWzYtX182XV0gW1tAKkAqKl1dIFtbQCoqQEBdXSBbW0AqKkAqXV0gW1tAKioqQF1dIFtbQCoqKipdXSBbWzZfLS02XV0gW1sqQEBAQF1dIFtbKkBAQCpdXSBbWypAQCpAXV0gW1sqQEAqKl1dIFtbKkAqQEBdXXwgMCAxIDIgMyA0IDUgNiA3IDggOSAwID8gKyA/ID8gfiA/ICwgLiBAID8gPyA/IHsgWyBdIH1bW1tfX19fXy0tXV1dW1tbX19fX18tLV1dXVtbW19fX19fLV9dXV1bW1tfX19fXy1fXV1d

The Decrypted form:

This string will be encrypted | a b c d e f g h i j k l m n o p q r s t u v w x y z| A B C D E F G H I J K L M N O P Q R S T U V W X Y Z| 0 1 2 3 4 5 6 7 8 9 0 ? + ? ? ~ ? , . @ ? ? ? { [ ] }
```

## License
This library uses the MIT license. For confidentiality reasons, the source code will not be made available for the first versions.
