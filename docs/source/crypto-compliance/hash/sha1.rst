SHA1
====


风险说明
--------

SHA1已被破解，攻击者能够针对快速伪造消息通过SHA1校验。

攻击案例
--------

`SHA-1 is a Shambles: First Chosen-Prefix Collision on SHA-1 and Application to the PGP Web of Trust <https://www.usenix.org/conference/usenixsecurity20/presentation/leurent>`_

合规建议
--------

- 新业务禁用SHA1，可选用SHA3-256，SHA256。
- 旧业务根据监管要求整改。

测试用例
---------

::

    $ echo -n 'justfortest' | openssl dgst -sha1 -hex
    SHA1(stdin)= 0ab00994c2451c712271df482dc15c5555cce606


参考资料
--------

- `iOS 13: SHA-1 signed certificates are no longer trusted for TLS <https://support.apple.com/en-us/103769>`_
- `NIST Transitioning Away from SHA-1 for All Applications <https://csrc.nist.gov/news/2022/nist-transitioning-away-from-sha-1-for-all-apps>`_

