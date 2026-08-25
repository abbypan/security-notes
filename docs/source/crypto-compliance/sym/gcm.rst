GCM
===

默认选用 AES/GCM/NoPadding 。


攻击案例
--------

`Samsung shipped '100 million' phones with flawed encryption <https://www.theregister.com/2022/02/23/samsung_encryption_phones/>`_


合规建议
--------

- GCM模式的默认IV长度为96 bits。
- 禁止使用固定IV。
- 会话过程中，禁止复用IV。
- 建议使用安全随机数做为IV。
- 选用GCM模式时，可以使用递增序列做为IV。


参考资料
--------

- `Trust Dies in Darkness: Shedding Light on Samsung's TrustZone Keymaster Design <https://eprint.iacr.org/2022/208.pdf>`_
- `Why AES-GCM Sucks <https://soatok.blog/2020/05/13/why-aes-gcm-sucks/>`_
