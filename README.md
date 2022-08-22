# cipher-xor.js

A simple yet effective encryption mechanism. When run once, the message is encrypted.
When run twice the message is restored.

## cipherXor

Encryption function. Takes a string secret which is used to generate a random number sequence which is then xor'd against
the message to created the encrypted digest.

```js
const encrypted = cipherXor("secret", "message")
console.log(encrypted)
```

Then to decrypt the message, run it through cryptoXor again:

```js
const message2 = cipherXor("secret", encrypted)
console.log("message should == ", message2)
```

## xorCipherHashPass

Generates a hash of the input. This is useful for checking that the user password is correct, without exposing what the password is. For example:

```js
const PASSWORD_VERIFICATION = "a4fed8c..."
const userPass = prompt("Enter password")
if (PASSWORD_VERIFICATION !== xorCipherHashPass(userPass)) {
  alert("password incorrect")
} else {
  alert("verified")
}

```

# Testing

Copy and paste the entire source file into the Chrome developer console then test that `cipherXor("secret", "message")` works, and that `xorCipherHashPass("secret")` works.
