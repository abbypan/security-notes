ECDH
======


攻击案例
--------

- `Breaking the Bluetooth Pairing – The Fixed Coordinate Invalid Curve Attack <https://eprint.iacr.org/2019/1043>`_

合规建议
--------

- EC Point格式优先选择Compressed模式。
- ECDH应检查EC Point是否在该曲线上。
- 建议优先选取Curve25519/448，其次选取secp r/k。

