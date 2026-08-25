Augmented PAKE
===========================

在无证书场景下，可采用OPAQUE、SPAKE2+、AuCPace等Augmented PAKE协议，用于终端password与对端的安全认证。

业务场景示例：
- 出厂预置，终端侧password，服务端侧校验信息。
- 服务端根据业务上下文临时生成，向终端侧下发password，向对端侧下发校验信息。


合规建议
--------

- 避免直接通过比较PIN码原文，进行不安全的初始化绑定。


参考资料
--------

- `The OPAQUE Augmented PAKE Protocol <https://datatracker.ietf.org/doc/draft-irtf-cfrg-opaque/>`_
- `RFC 9383 SPAKE2+, an Augmented Password-Authenticated Key Exchange (PAKE) Protocol <https://www.rfc-editor.org/rfc/rfc9383.html>`_
- `AuCPace, an augmented PAKE <https://datatracker.ietf.org/doc/draft-haase-aucpace/>`_

