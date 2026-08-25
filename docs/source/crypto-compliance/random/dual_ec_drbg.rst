Dual_EC_DRBG
============


风险说明
--------

Dual_EC_DRBG存在隐藏安全缺陷，可能导致加密效果变弱，降低密文破解的难度。

攻击案例
--------

`NSA paid $10 Million bribe to RSA Security for Keeping Encryption Weak <https://thehackernews.com/2013/12/nsa-paid-10-million-bribe-to-rsa.html>`_


合规建议
--------

- 禁止选用Dual_EC_DRBG生成随机数。
- 推荐选用CTR-DRBG。


参考资料
--------

`Dual EC: A Standardized Back Door <https://eprint.iacr.org/2015/767.pdf>`_

