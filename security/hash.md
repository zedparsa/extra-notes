## 🔑 Hash function

### 💬Conversation
Before we define what a hash is, let’s see what this conversation is all about :

 **Parsa:**  
> A hash function is a type of **one-way function**.

🗨 <div align="right"><strong>:Yazdan</strong>  
> What does “one-way function” mean?  
</div>

 **Parsa:**  
> Let me give you an example: imagine you have a meat grinder.  
> You put meat into it and it grinds it.  
> Now, can you put ground meat back and get whole cuts? No.  
> That’s a one-way function.

🗨 <div align="right"><strong>:Yazdan</strong>  
> Okay, I understand that. What does a hash do?  
</div>

 **Parsa:**  
> A hash converts any input into a fixed-length output.  
> You can’t easily go backwards from the output.

🗨 <div align="right"><strong>:Yazdan</strong>  
> Where is it used? Why was such a function created?  
</div>

 **Parsa:**  
> It's used to verify data, check if files have changed, and keep systems secure.

🗨 <div align="right"><strong>:Yazdan</strong>  
> Can you give me an example for each? Especially for security.  
</div>

 **Parsa:**  
> Absolutely. But first, let me show you the shape of a hash:  
>  
> ```
> Input  ─────────▶ [ Hash Function ] ─────────▶ Fixed-Length Output
> ```  

### 🔹 What is a Hash Function?
- **Here’s definition of a hash function** :
> A hash function is a one-way mathematical process that takes any input and turns it into a fixed-length, seemingly random output.
It’s designed so that:
> - You can’t reverse it,
> - Small input changes cause big output changes,
> - And it’s almost impossible to find two different inputs with the same output.
> - Think of it as a digital fingerprint: unique, irreversible, and fixed in size — no matter how big the original data is.

### 🔧 Use Cases

#### 🔐 **Security:**  
When you create a password for a website, it stores the hash of your password—not the password itself.  
So even if someone hacks the site, they can’t see your real password.

📦 **Data integrity:**  
When you download a file from a website, the site gives you a hash. After downloading, your computer calculates the hash again.  
If the two hashes match, the file has not been changed or damaged.

✍️ **Digital signatures:**  
When someone signs a document digitally, the computer first creates a hash of the document. Then it encrypts that hash.  
This lets the receiver verify that the document hasn’t been altered and truly comes from the sender.

⚡ **Power systems:**  
In smart power systems or IoT, hashes are used to make sure data from sensors or devices hasn’t been changed during transmission.  
This keeps control systems safe from tampering.

### 🔐 Three Popular Hash Functions
- ✅ SHA‑256
> - SHA-256 stands for Secure Hash Algorithm – 256-bit. It’s part of the SHA‑2 family and is widely used in modern security systems.
> - It takes any input and produces a fixed 256-bit hash.
> - Even a tiny change in the input results in a completely different output.
> - It’s currently considered secure and collision-resistant.
> - Used in blockchains (like Bitcoin), digital signatures, and file integrity checks.

```
SHA-256("hello") →  
2cf24dba5fb0a30e26e83b2ac5b9e29e1b161e5c1fa7425e73043362938b9824
```
> 👉 If you want a reliable and strong hash for security purposes (but not for storing passwords), SHA‑256 is a solid choice.

- ✅ bcrypt
> - bcrypt is a special type of hash function designed for password hashing. Unlike SHA-256 or MD5, it’s not meant for speed — it’s intentionally slow.
> - It includes a built-in salt, making hashes unique even for the same input.
> - It's configurable — you can control how slow it runs (called the cost factor).
> - It’s resistant to brute-force attacks, even with powerful GPUs.
> - Still one of the most trusted methods for securely storing passwords in databases.

```
bcrypt("Pa$$w0rd") →
$2b$12$kixQHgpF8Y77wIUZ5uYROeFvbcZrwT/jWk1.G6hdgMO7S2HeVJ89G
```
> 👉 If you're dealing with user authentication, always use bcrypt instead of general-purpose hash functions.

- ⚠️ MD5
> - MD5 (Message Digest 5) is a fast and lightweight hash function, but it’s no longer secure for cryptographic purposes.
> - It generates a 128-bit hash.
> - Was very popular in the past for file checksums and digital signatures.
> - But today, it’s broken: attackers can create two different inputs with the same hash (this is called a collision).
> - Still used for non-security tasks, like verifying file downloads or quick data fingerprinting.

```
MD5("hello") →
5d41402abc4b2a76b9719d911017c592
```
> 👉 Never use MD5 for storing passwords or signing data. It's fine for quick, non-sensitive integrity checks only.
