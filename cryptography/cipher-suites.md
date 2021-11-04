## AWS ELB Security Policies

You can view supported "security policies" for an Amazon ALB by going to [this page](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/create-tls-listener.html).
It shows a map from the name of the policy to what cipher suites are supported by that policy.

## Choosing Cipher Suites

There is some debate as to whether ChaCha20 or AES256 (with GCM) is the better choice for a symmetric stream cipher.
ChaCha20 is now used as part of QUIC (HTTP3), and is considered to have better safety margins than AES.
Both use 256-bit keys.
However, others believe AES-256 offers better performance due to support in hardware and better parallelizability (there are hardware instructions for AES in modern x86 architectures).
Still others say that many implementations of AES are flawed, since it is easy to make a mistake.
There is an interesting discussion on the trade-offs [in this Reddit thread](https://www.reddit.com/r/crypto/comments/f7c2nv/chacha20_v_aes256/).
