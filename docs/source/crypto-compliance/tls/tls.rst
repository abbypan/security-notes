TLS
===


攻击案例
--------

- `Security Flaws Induced by CBC Padding Applications to SSL, IPSEC, WTLS... <https://www.iacr.org/cryptodb/archive/2002/EUROCRYPT/2850/2850.pdf>`_
- `Scalable Scanning and Automatic Classification of TLS Padding Oracle Vulnerabilities <https://www.usenix.org/system/files/sec19-merget.pdf>`_
- `The ROBOT Attack <https://robotattack.org/>`_



合规建议
--------

- 禁止使用低于TLS v1.2的旧版TLS。
- 禁止选用含MD5/RC4/DES/SHA1等过时算法的TLS ciphersuite。
- 禁止选用含CBC算法的TLS ciphersuite。
- 禁止选用含TLS-RSA关键字，且不含PSK关键字的TLS ciphersuite。
- 避免选用DHE的TLS ciphersuite，防范Weak DH的场景。
- TLS是传输层安全协议，仅用TLS无法满足数据层加密的合规要求，应考虑选择数据信封等方案。
- 推荐选用Mutual TLS，基于双向证书建立TLS安全信道。


参考资料
--------

- `Cipher Suites <https://ciphersuite.info/cs/>`_
- `Disabling SSLv3 and RC4 <https://security.googleblog.com/2015/09/disabling-sslv3-and-rc4.html>`_
- `RFC 8996 Deprecating TLS 1.0 and TLS 1.1 <https://www.rfc-editor.org/rfc/rfc8996>`_
- `RFC 9155 Deprecating MD5 and SHA-1 Signature Hashes in TLS 1.2 and DTLS 1.2 <https://datatracker.ietf.org/doc/rfc9155/>`_
- `Deprecating Obsolete Key Exchange Methods in TLS 1.2 <https://datatracker.ietf.org/doc/draft-ietf-tls-deprecate-obsolete-kex/>`_

