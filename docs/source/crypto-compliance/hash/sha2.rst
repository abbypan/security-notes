SHA2
====


合规建议
--------

- 默认选用SHA256，或者选用SHA384、SHA512等。


测试用例
-----------

::

    $ echo -n 'justfortest' | openssl dgst -sha256 -hex
    SHA2-256(stdin)= 15ce1e190f07f3d0c4d28b0c4064704a27374b9e53f9c3a0035ff8281d27eddf


