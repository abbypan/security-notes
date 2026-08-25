SHA3
====



合规建议
--------

- 默认选用SHA3-256，或者选用SHA3-384、SHA3-512等。


测试用例
-----------

::

      $ echo -n 'justfortest' | openssl dgst -sha3-256 -hex
      SHA3-256(stdin)= 87e5235f73203a1822277cddf4da2e84f917bfe301cdb6243a6bc4ef8b5f31d8

