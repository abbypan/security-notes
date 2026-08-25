CRC
===


风险说明
--------

CRC已被破解, CRC不是Hash算法。


合规建议
--------

- CRC系列算法仅用于快速检测文件、消息传输错误。
- 文件完整性、消息完整性的场景，应选用Hash算法，禁止选用CRC。


测试用例
-----------

::
 
    $ cpanm Archive::Zip
    $ echo -n 'justfortest' | crc32 /dev/stdin
    43458719


参考资料
--------

`zip-crc-cracker <https://github.com/kmyk/zip-crc-cracker>`_


