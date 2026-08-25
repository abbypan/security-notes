Private Key(私钥)
==================

合规建议
--------

- Private Key应安全存储，避免篡改，禁止公开，避免泄漏。
- Private Key安全强度不得低于128 bits。
- 禁止将Private Key硬编码在代码或者配置文件中。
- 禁止将Private Key拆分成多个片断，硬编码在代码或者配置文件中。
- 禁止将Private Key与密文一起传输。
- 禁止将Private Key与密文一起存储在数据库或者文件中。
- 禁止使用Private Key加密明文，再使用已公开的公钥解密密文。


