### Backend interview questions everyone must know:

<details>
  <summary><strong>
    Explain JSON Web Token (JWT) Structure
  </summary>
Structure:</strong> Header.Payload.Signature
- **Header**:  
  A Base64URL-encoded JSON object that describes the token type and the signing algorithm used.

  Example:
  ```
  {
    "alg": "HS256", // Algorithm used for signing (e.g., HMAC SHA256)
    "typ": "JWT"    // Token type
  }
  ```

  Encoded as:  
  eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9

- **Payload**:  
  The payload is a Base64URL-encoded JSON object containing the **claims**. Claims are statements about the user or additional metadata.  

  Types of Claims:
  - **Registered Claims**: Predefined keys like:
    - iss (Issuer)  
    - sub (Subject)  
    - exp (Expiration Time)  
  - **Public Claims**: Custom data, e.g., email, role.  
  - **Private Claims**: Custom data agreed between sender and receiver.

  Example:
  ```
  {
    "sub": "1234567890", // Subject (e.g., user ID)
    "name": "John Doe",  // Custom claim
    "iat": 1516239022    // Issued at timestamp
  }
  ```

  Encoded as:  
  eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ

- **Signature**:  
  The signature ensures the integrity of the token. It is generated using the following:

  ```
  HMACSHA256(
    base64UrlEncode(header) + "." + base64UrlEncode(payload),
    secret
  )
  ```

  Example signature:  
  SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c

</details>
