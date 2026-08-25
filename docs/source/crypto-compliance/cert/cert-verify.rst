证书安全
==================================


证书安全检查
------------

终端实体(EE, End Entity)证书(Certificate)的安全检查：

1. trust Manager: 初始化可信的Root CA。

#. verify: 检查该EE Certificate是否在可信Root CA下的Certificate Chain内的中间CA签发。

#. checkValidity: 检查Root CA Certificate -- Intermediate CA Certificate -- EE Certificate 证书的有效期。

#. 内容检查: 检查EE Certificate中的证书域内容是否与预期相符，例如Subject Common Name, Subject Alt Names, Issuer Name, Key Usages, Extended Key Usages等。



合规建议
--------
- 终端必须对服务端证书进行安全检查。
- 禁止将TLS的默认证书检查函数重置为空函数。
- 终端根据业务实际情况，检查EE Certificate的证书内容是否符合预期。
- 禁止将业务自有Root CA与系统预置的Common CA List合入同一个trust Manager，引入证书劫持风险。


参考资料
--------

- `Common CA Database <https://www.ccadb.org/>`_

