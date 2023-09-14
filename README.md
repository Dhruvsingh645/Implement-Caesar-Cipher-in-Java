# Implement-Caesar-Cipher-in-Java
Project Name: DRDO Cryptography and Cryptanalysis Project  
Task Name: Implement Caesar Cipher in Java

## Introduction:

In an increasingly digital world where the security of sensitive information is paramount, the "DRDO Cryptography and Cryptanalysis Project" stands as a beacon of innovation and data protection. As part of this endeavor, our task is to delve into the timeless realm of cryptography by implementing the classic Caesar Cipher in the Java programming language.

### Caesar Cipher:

The Caesar Cipher—named after Julius Caesar, who is believed to have used it to secure his confidential messages—is a simple yet historically significant substitution cipher. It operates by shifting each letter of the plaintext by a fixed number of positions down the alphabet. In this project, we embark on a journey to not only understand the mechanics of this cipher but also to implement it in Java, demonstrating its application in modern information security.


### Objectives:

<b>Implement Caesar Cipher:</b> Develop a Java program that can both encrypt and decrypt messages using the Caesar Cipher.

<b>User Interaction:</b> Create an interactive interface that allows users to input plaintext and choose a shift value for encryption.

<b>Encryption and Decryption:</b> Showcase the process of encrypting plaintext into ciphertext and decrypting ciphertext back into its original form.

<b>Educational Tool:</b> Provide a practical example of a classic encryption technique for educational purposes, enabling enthusiasts to explore the foundations of cryptography.

As we progress in this project, we'll not only gain a deeper understanding of the Caesar Cipher's inner workings but also contribute to the broader mission of the DRDO Cryptography and Cryptanalysis Project—strengthening national security through research, innovation, and the protection of sensitive information.



```
public static String encrypt(String plainText, int shiftKey)
{
    plainText = plainText.toLowerCase();
    String cipherText = "";
    for (int i = 0; i < plainText.length(); i++)
    {
        int charPosition = ALPHABET.indexOf(plainText.charAt(i));
        int ogvalue = (shiftKey + charPosition) % 26;
        char replaceValue = ALPHABET.charAt(ogvalue);
        cipherText += replaceValue;
    }
    return cipherText;
}

public static String decrypt(String cipherText, int shiftKey)
{
    cipherText = cipherText.toLowerCase();
    String plainText = "";
    for (int i = 0; i < cipherText.length(); i++)
    {
        int charPosition = ALPHABET.indexOf(cipherText.charAt(i));
        int ogvalue = (charPosition - shiftKey) % 26;
        if (ogvalue < 0)
        {
            ogvalue = ALPHABET.length() + ogvalue;
        }
        char replaceVal = ALPHABET.charAt(ogvalue);
        plainText += replaceVal;
    }
    return plainText;
}

public static void main(String[] args)
{
    Scanner sc = new Scanner(System.in);
    System.out.println("Enter the String for Encryption: ");
    String message = new String();
    message = sc.next();
    System.out.println(encrypt(message, 3));
    System.out.println(decrypt(encrypt(message, 3), 3));
    sc.close();
}
```

<h2>Link of my PPT you can Refers this<h2> :- https://shorturl.at/bMW14
