RSAES-PKCS-v1_5
===============

JAVA库一般称为RSA/ECB/PKCS1Padding，RSA/NONE/PKCS1Padding。

风险说明
--------

RSAES-PKCS-v1_5存在padding oracle attack的风险，攻击者通过修改密文反复请求解密来测试padding，最终在不知道密钥的情况下成功解密。

攻击案例
--------

`Efficient Padding Oracle Attacks on Cryptographic Hardware <https://eprint.iacr.org/2012/417.pdf>`_


合规建议
--------

- 避免选用RSAES-PKCS-v1_5，以RSAES-OAEP替代。
- NIST SP800-131Ar2，2023/12/31后禁用RSAES-PKCS-v1_5, 3DES。


参考资料
--------

`Practical Padding Oracle Attacks on RSA <https://secgroup.dais.unive.it/wp-content/uploads/2012/11/Practical-Padding-Oracle-Attacks-on-RSA.html>`_

