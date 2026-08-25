Random Reuse
============


风险说明
--------

随机数复用可能导致密钥泄漏等高风险后果。

攻击案例
--------

- `Samsung shipped '100 million' phones with flawed encryption <https://www.theregister.com/2022/02/23/samsung_encryption_phones/>`_
- `iPhone hacker publishes secret Sony PlayStation 3 key <https://www.bbc.com/news/technology-12116051>`_
- `Polynonce: A Tale of a Novel ECDSA Attack and Bitcoin Tears <https://research.kudelskisecurity.com/2023/03/06/polynonce-a-tale-of-a-novel-ecdsa-attack-and-bitcoin-tears/>`_


合规建议
--------

- 禁止随机数复用。
- 通信双方应各自独立生成安全随机数。


参考资料
--------

- `Trust Dies in Darkness: Shedding Light on Samsung's TrustZone Keymaster Design <https://eprint.iacr.org/2022/208.pdf>`_
- `Key Discovery in ECDSA: Understanding Implementation and Security Risk <https://hacken.io/insights/ecdsa/>`_
- `ECDSA Nonce Reuse Attack <https://notsosecure.com/ecdsa-nonce-reuse-attack>`_

