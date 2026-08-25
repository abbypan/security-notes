ECB
===


风险说明
--------

攻击者尝试修改密文，绕过某些重放限制，执行风险操作。

攻击案例
--------

`CVE-2022-28382 <https://nvd.nist.gov/vuln/detail/CVE-2022-28382>`_


合规建议
--------

- 禁用ECB模式，选用CTR、GCM等模式。


参考资料
--------

`aes-ecb-attacks <https://github.com/emilystamm/aes-ecb-attacks>`_

