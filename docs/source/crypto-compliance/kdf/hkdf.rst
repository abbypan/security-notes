HKDF
=======


合规建议
--------

- 默认选用SHA256做为HKDF的Hash函数，或者选用其他更高安全强度的Hash函数等。


示例代码
-----------

`https://github.com/abbypan/crypto-utils/tree/master/hkdf <https://github.com/abbypan/crypto-utils/tree/master/hkdf>`_

.. code-block:: perl

    #!/usr/bin/perl

    use Crypt::KeyDerivation ':all';

    my ($password_hexstr, $salt_hexstr, $info, $byte_len, $hash_name) = @ARGV;

    my $password = pack("H*", $password_hexstr);
    my $salt = pack("H*",$salt_hexstr);

    my $okm = hkdf($password, $salt, $hash_name, $byte_len, $info);

    my $okm_hexstr = unpack("H*", $okm);
    printf("%s\n", $okm_hexstr);



测试用例
-----------

RFC5869

::

    key_hexstr: a27e195cf3ea9755eceb1f77ca0dd20ba1fdaa8832f1b2fb637c8912ad3dce13 
    salt_hexstr: dc4dab0be272e8e85afb0aa1d423813bf9a5a2c31d14dd231992aabb4f6fc6f0 
    info: somelabel 
    okm_len: 32 
    hash: SHA256
    okm_hexstr: f1bf30afd3f7c964a750244ff2e1daed8ad130fe12ff2cb844bd9d556c10e39e


参考资料
--------

- `RFC5869: HMAC-based Extract-and-Expand Key Derivation Function (HKDF) <https://datatracker.ietf.org/doc/html/rfc5869>`_
