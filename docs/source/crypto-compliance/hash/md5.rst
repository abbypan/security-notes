MD5
===


风险说明
--------

2005年，MD5已被破解，攻击者能够针对快速伪造消息通过MD5校验。

攻击案例
--------

- `Finding Preimages in Full MD5 Faster Than Exhaustive Search <https://link.springer.com/chapter/10.1007/978-3-642-01001-9_8>`_
- `MD5 Considered Harmful Today Creating a rogue CA certificate <https://fahrplan.events.ccc.de/congress/2008/Fahrplan/attachments/1251_md5-collisions-1.0.pdf>`_


合规建议
--------

- 新业务禁用MD5，可选用SHA3-256，SHA256。
- 旧业务根据监管要求整改。


测试用例
-----------

::

    $ echo -n 'justfortest' | openssl dgst -md5 -hex
    MD5(stdin)= c830df6e9ba06988d27a14fc679e24c9


参考资料
--------

`MD5 and SHA-1 Collision Attacks: A Tutorial <http://koclab.cs.ucsb.edu/teaching/cren/project/2008/savage.pdf>`_

