RSAES-OAEP
==========

JAVA库一般称为RSA/ECB/OAEPPadding，RSA/NONE/OAEPPadding。

风险说明
--------

RSA/ECB/OAEPPadding存在ECB关键字，可能触发扫描器误报。

合规建议
--------

- 将RSA/ECB/OAEPPadding文本替换为RSA/NONE/OAEPPadding。
