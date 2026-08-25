ECC
====




开发细节
--------

- ECC签名算法的密钥位长与HASH位长匹配，例如ECDSA (NIST P-256) with SHA256, ECDSA (NIST P-384) with SHA384 等。


合规建议
--------

- ECC密钥位长不低于256，或者可选用更高强度的384等。
- ECC Point 优先选择Compressed模式，而非Uncompressed模式。
- NIST IR 8547, ecc 2030 deprecated, 2035 disallowed。


数字签名
--------

::

   openssl dgst -sha256 -sign ecc_priv.pem -out data.sig data.txt
   openssl dgst -sha256 -verify ecc_pub.pem -signature data.sig data.txt
