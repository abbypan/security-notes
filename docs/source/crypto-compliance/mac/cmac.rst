AES-CMAC
==========

嵌入式业务场景可能使用AES-CMAC。

例如蓝牙场景下 CCM = CTR + CMAC。

示例代码
-----------

`https://github.com/abbypan/crypto-utils/tree/master/aes-cmac <https://github.com/abbypan/crypto-utils/tree/master/aes-cmac>`_

.. code-block:: c

    #include <stdio.h>
    #include <string.h>
    #include <openssl/crypto.h>
    #include <openssl/cmac.h>

    int main(int argc, char *argv[])
    {

        long key_len;
        unsigned char *key = OPENSSL_hexstr2buf(argv[1], &key_len);

        long data_len;
        unsigned char *data = OPENSSL_hexstr2buf(argv[2], &data_len);

        unsigned char mac[16] = {0}; 
        size_t mac_len;

        CMAC_CTX *ctx = CMAC_CTX_new();
        CMAC_Init(ctx, key, 16, EVP_aes_128_cbc(), NULL);

        CMAC_Update(ctx, data, data_len);
        CMAC_Final(ctx, mac, &mac_len);

        char *mac_hexstr = OPENSSL_buf2hexstr(mac, (long) mac_len);

        printf("key_hexstr: %s\ndata_hexstr: %s\naes-128-cmac_hexstr: %s\n", argv[1], argv[2], mac_hexstr);

        CMAC_CTX_free(ctx);

        OPENSSL_free(key);
        OPENSSL_free(data);
        OPENSSL_free(mac_hexstr);

        return 0;
    }


测试用例
-----------

RFC4493 

::

    K              2b7e1516 28aed2a6 abf71588 09cf4f3c
    M              6bc1bee2 2e409f96 e93d7e11 7393172a
                   ae2d8a57 1e03ac9c 9eb76fac 45af8e51
                   30c81c46 a35ce411
    AES-CMAC       dfa66747 de9ae630 30ca3261 1497c827


参考资料
--------

- `RFC 4493: The AES-CMAC Algorithm <https://www.rfc-editor.org/rfc/rfc4493.html>`_

