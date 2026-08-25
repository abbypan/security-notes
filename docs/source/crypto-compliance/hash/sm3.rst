SM3
====



合规建议
--------

- 国密场景下选用SM3。


测试用例
-----------

::

    $ echo -n 'justfortest' | openssl dgst -sm3 -hex     
    SM3(stdin)= bee732ab14c11af108eb112d949a26666efa6a9dc5135ee032aae5a75a9d3c52
