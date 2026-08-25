BASE64
======


风险说明
--------

BASE64是编解码算法，不是加解密算法。

BASE64无法用于保护业务敏感数据。


攻击案例
--------

`CVE-2022-3206 <https://nvd.nist.gov/vuln/detail/CVE-2022-3206>`_


合规建议
--------

- 在需要保护业务敏感数据时，选用AES、RSA、ECC等加解密方案，而不是选用BASE64编码。

参考资料
--------

`Base64 is not encryption <https://sempf.net/post/base64-is-not-encryption>`_

