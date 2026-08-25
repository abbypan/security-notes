Key(对称密钥)
=============


风险说明
--------

如果攻击者获取Key，则能够解密该Key加密过的所有Ciphertext获得Plaintext，导致数据泄漏。

合规建议
--------

- Key应安全存储，避免篡改，避免泄漏。
- Key长度不得低于128 bits，推荐 256 bits。
- 禁止将Key硬编码在代码或者配置文件中。
- 禁止将Key拆分成多个片断，硬编码在代码或者配置文件中。
- 禁止将Key与密文一起传输。
- 禁止将Key与密文一起存储在数据库或者文件中。
- 禁止设置与Key相同的固定IV。

doc
-----
- `BSI TR-02102-1 Cryptographic Mechanisms: Recommendations and Key Lengths <https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/TechGuidelines/TG02102/BSI-TR-02102-1.pdf?__blob=publicationFile&v=10>`_
