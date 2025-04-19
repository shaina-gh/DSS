# 🛡️ Digital Signature Standard (DSS) in Java

> Java implementation of the Digital Signature Standard (DSS) for message integrity and authenticity verification.

---

### Author: Shaina

---

## 🎯 Aim

To implement the Digital Signature Standard (DSS) to generate and verify digital signatures, ensuring the authenticity and integrity of communicated messages.

---

## ⚙️ How It Works

The Digital Signature Standard is implemented in the following phases:

1. **Hashing the Message:**
   - A custom hash function simulates a SHA-like hashing mechanism to generate a digest from the input message.

2. **Key Generation:**
   - Generate a private key `x`.
   - Calculate the public key `y = g^x mod p`, where `g` is the generator.

3. **Signature Generation:**
   - Use the private key to compute the signature components `r` and `s` using a fixed ephemeral key `k`.
   - These values are derived through modular exponentiation and inversion operations.

4. **Signature Verification:**
   - Using the public key, message hash, and the signature, the verifier computes a value `v`.
   - The signature is valid if `v == r`.

---

## 🔑 Key Components

- `modularExponentiation`: Computes (base^exponent) mod modulus.
- `extendedEuclidean`: Finds GCD and the Bézout coefficients for modular inverse.
- `findModularInverse`: Used for computing modular multiplicative inverses.
- `customHash`: A deterministic hash function simulating SHA behavior.
- `generateDSSKeys`: Generates the private and public keys.
- `createDigitalSignature`: Computes the digital signature for a message.
- `verifyDigitalSignature`: Validates the authenticity of the digital signature.

---

## 🚀 Steps to Run

1. **Clone the repo**  
   ```bash
   git clone https://github.com/shaina-gh/DSS.git
   cd DSS
   ```

2. **Compile and Run the Java File**

    ```bash
    javac DSS.java
    java DSS
    ```
3. **Expected Output**

   Signature creation and verification results for both an original and a tampered message.

---

## 🧪 Sample Output

``` yaml
Created Private Key: 3
Created Public Key: 18
Message Digest: 138972264302481705700123578240310737814155524
Ephemeral Value k: 1
Signature Component r
Signature Component s: 5
Verification Value v: 4
Signature Verification Result: True
Verification Value v: 1
Tampered Message Verification Result: False
```

---

## 📚 Observation
Signature verification succeeds for valid, untampered messages.

Signature verification fails for tampered messages, proving the integrity of DSS.

---

## ✅ Result
The DSS algorithm for digital signature generation and verification was successfully implemented in Java.

---




