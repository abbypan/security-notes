Textbook RSA 
============

Textbook RSA，或者称为RSA without Padding，RSA NoPadding。

JAVA库一般称为RSA/ECB/NoPadding，RSA/NONE/NoPadding。

风险说明
--------

Textbook RSA存在被暴力破解风险，攻击者无需入侵服务器，通过暴力破解运算获得RSA私钥。

攻击案例
--------

`When Textbook RSA is Used to Protect the Privacy of Hundreds of Millions of Users <https://arxiv.org/pdf/1802.03367>`_


合规建议
--------

- 禁止选用Textbook RSA，以RSAES-OAEP替代。


参考资料
--------

`Textbook RSA And its insecurities <https://cs.wellesley.edu/~cs310/lectures/26_rsa_slides_handouts.pdf>`_


