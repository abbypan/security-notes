RSAES-OAEP + AES
=================


开发细节
--------

加密方：

1. 安全随机生成对称密钥Key。

#. 使用RSAES-OAEP加密Key，获得cipherKey。

#. 使用Key对明文plaintext做AES加密，获得ciphertext。


合规建议
--------

- plaintext长度应低于RSA模长。
- 禁止将超过RSA模长的plaintext拆分成数组，对数组元素重复调用RSAES-OAEP加密。应选用数字信封，例如RSAES-OAEP + AES。

