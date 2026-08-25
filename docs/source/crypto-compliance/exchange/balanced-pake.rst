Balanced PAKE
===========================

1. 安全初始化

 - 业务初始化绑定时，可采用CPace、SPAKE2等Balanced PAKE协议，通过用户扫二维码、或手动输入PIN码等方式，建立安全信道。

 - 在安全信道环境下，双方交换自身Long-Term Public Key。

#. 后续安全通信 

  - 基于初始化安全交换的Long-Term Public Key，建立AKE安全通信。


合规建议
--------

- J-PAKE可满足安全要求，但考虑时延与性能，不建议采用J-PAKE。


参考资料
--------

- `CPace, a balanced composable PAKE <https://datatracker.ietf.org/doc/draft-irtf-cfrg-cpace/>`_
- `RFC 9382 SPAKE2, a Password-Authenticated Key Exchange <https://www.rfc-editor.org/rfc/rfc9382.html>`_
