IV (初始向量)
==============

参考 `Random Reuse <../random/random-reuse.html>`_ 。

风险说明
--------

固定IV可能导致黑客破解对称密钥、或者无需知道密钥构造风险指令的密文，导致业务数据泄漏、或者接收方执行风险操作。

攻击案例
--------

`Samsung shipped '100 million' phones with flawed encryption <https://www.theregister.com/2022/02/23/samsung_encryption_phones/>`_


合规建议
--------

- 禁止使用固定IV。
- 会话过程中，禁止复用IV。
- 使用安全随机数做为IV。
- 可以在会话密钥协商时，同时派生Key和IV，此时无需传输IV。
- 选用CTR、CCM、GCM模式时，可以使用递增序列做为IV。
- IV无需保密。
- 如果IV与Key通过密钥协商派生，则无需传输IV。


参考资料
--------

`Trust Dies in Darkness: Shedding Light on Samsung's TrustZone Keymaster Design <https://eprint.iacr.org/2022/208.pdf>`_

