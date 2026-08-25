HMAC
=======



合规建议
--------

- 默认选用HMAC-SHA256，或者选用其他更高安全强度的HASH函数等。


示例代码
-----------

`https://github.com/abbypan/crypto-utils/tree/master/hmac <https://github.com/abbypan/crypto-utils/tree/master/hmac>`_

.. code-block:: perl 

    #!/usr/bin/perl

    use Digest::SHA qw/hmac_sha256/;

    my ($key_hexstr, $data_hexstr) = @ARGV;

    $key_bin = pack("H*", $key_hexstr);
    $data_bin = pack("H*", $data_hexstr);

    my $mac_bin = hmac_sha256($data_bin, $key_bin);
    my $mac_hexstr = unpack("H*", $mac_bin);

    printf("key_hexstr: %s\ndata_hexstr: %s\nhmac-sha256_hexstr: %s\n", $key_hexstr, $data_hexstr, $mac_hexstr);


测试用例
-----------

RFC4231

::

    key_hexstr: 0b0b0b0b0b0b0b0b0b0b0b0b0b0b0b0b0b0b0b0b
    data_hexstr: 4869205468657265
    hmac-sha256_hexstr: b0344c61d8db38535ca8afceaf0bf12b881dc200c9833da726e9376c2e32cff7


参考资料
-----------

- `RFC2104 HMAC: Keyed-Hashing for Message Authentication <https://datatracker.ietf.org/doc/html/rfc2104>`_
- `RFC4231 Identifiers and Test Vectors for HMAC-SHA-224, HMAC-SHA-256, HMAC-SHA-384, and HMAC-SHA-512 <https://datatracker.ietf.org/doc/html/rfc4231>`_

