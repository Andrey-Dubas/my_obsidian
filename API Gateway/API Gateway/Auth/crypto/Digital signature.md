A **digital signature** is a mathematical scheme for verifying the authenticity of digital messages or documents. A valid digital signature on a message gives a recipient confidence that the message came from a sender known to the recipient.

[![Alice signs a message—"Hello Bob!"—by appending a signature computed from the message and her private key. Bob receives the message, including the signature, and using Alice's public key, verifies the authenticity of the signed message.](https://upload.wikimedia.org/wikipedia/commons/thumb/7/78/Private_key_signing.svg/220px-Private_key_signing.svg.png)](https://en.wikipedia.org/wiki/File:Private_key_signing.svg)

Digital signatures are a standard element of most [cryptographic protocol](https://en.wikipedia.org/wiki/Cryptographic_protocol) suites


A digital signature scheme typically consists of three algorithms:

- A _[key generation](https://en.wikipedia.org/wiki/Key_generation "Key generation")_ algorithm that selects a _private key_ [uniformly at random](https://en.wikipedia.org/wiki/Uniform_distribution_(discrete) "Uniform distribution (discrete)") from a set of possible private keys. The algorithm outputs the private key and a corresponding _public key_.
- A _signing_ algorithm that, given a message and a private key, produces a signature.
- A _signature verifying_ algorithm that, given the message, public key and signature, either accepts or rejects the message's claim to authenticity.


Two main properties are required:
First, the authenticity of a signature generated from a fixed message and fixed private key can be verified by using the corresponding public key.
Secondly, it should be computationally infeasible to generate a valid signature for a party without knowing that party's private key. A digital signature is an authentication mechanism that enables the creator of the message to attach a code that acts as a signature. The [Digital Signature Algorithm](https://en.wikipedia.org/wiki/Digital_Signature_Algorithm "Digital Signature Algorithm") (DSA), developed by the [National Institute of Standards and Technology](https://en.wikipedia.org/wiki/National_Institute_of_Standards_and_Technology "National Institute of Standards and Technology"), is one of [many examples](https://en.wikipedia.org/wiki/Digital_signature#Some_digital_signature_algorithms) of a signing algorithm.

![[m9mct719.bmp]]

Sender:
 - sender hashes data
 - the generated hash is signed (encrypted?) with private key. The result is signature
 - both data and signature is sent to recipient
 Recipient:
 - takes data and put it as input to hashing function. Let's call the output as H1
 - takes signature, decrypt it with a public key -> gets hash (H2)
 - H1 == H2 -> verified!