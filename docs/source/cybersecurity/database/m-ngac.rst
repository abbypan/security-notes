m-NGAC
####################

简介
====================

m-NGAC（embedded Next Generation Access Control）将 ANSI/INCITS NGAC
访问控制框架直接嵌入关系型数据库，在数据所在的位置统一保存并执行一致的访问控制策略。
它不依赖应用层逐一实现鉴权。

m-NGAC 面向细粒度数据库访问控制，可对行、列和字段级数据进行保护，并支持跨多个数据库集中管理策略。
其目标是减少应用层访问控制逻辑，降低绕过策略的风险，同时尽量保持原有 SQL 查询逻辑不变。

NIST 文档
====================

- `NIST IR 8611: m-NGAC: Transcending Traditional Database Security Models <https://doi.org/10.6028/NIST.IR.8611>`_
 
- `NIST CSRC 发布说明：m-NGAC: Transcending Traditional Database Security Models <https://csrc.nist.gov/News/2026/transcending-traditional-database-security-models>`_：
 
- `NIST 专利说明：Achieving Out-of-the-box Fine-Grained Access Control in Databases <https://www.nist.gov/patents/achieving-out-box-fine-grained-access-control-databases-enforcing-and-embedding-next>`_：
 

