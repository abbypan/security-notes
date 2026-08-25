KMAC
##########

- 默认选用KMAC128，或者KMAC256。
- KMAC的XOF模式支持任意长度的输出，例如KMACXOF128，KMACXOF256。


示例代码
***********

`https://github.com/abbypan/crypto-utils/tree/master/kmac <https://github.com/abbypan/crypto-utils/tree/master/kmac>`_

.. code-block:: c

    #include <stdio.h>
    #include <string.h>
    #include <openssl/core_names.h>
    #include <openssl/params.h>
    #include <openssl/evp.h>
    #include <openssl/crypto.h>


    static int do_kmac(const unsigned char *in, size_t in_len,
            const unsigned char *key, size_t key_len,
            const unsigned char *custom, size_t custom_len,
            int xof_enabled, unsigned char *out, int out_len)
    {

        // https://docs.openssl.org/3.2/man7/EVP_MAC-KMAC/

        EVP_MAC_CTX *ctx = NULL;
        EVP_MAC *mac = NULL;
        OSSL_PARAM params[4], *p;
        int ret = 0;
        size_t l = 0;

        /*mac = EVP_MAC_fetch(NULL, "KMAC-128", NULL);*/
        mac = EVP_MAC_fetch(NULL, "KMAC-128", "provider=default");
        if (mac == NULL)
            goto err;
        ctx = EVP_MAC_CTX_new(mac);

        EVP_MAC_free(mac);
        if (ctx == NULL)
            goto err;

        p = params;
        *p++ = OSSL_PARAM_construct_octet_string(OSSL_MAC_PARAM_KEY,
                (void *)key, key_len);
        if (custom != NULL && custom_len != 0)
            *p++ = OSSL_PARAM_construct_octet_string(OSSL_MAC_PARAM_CUSTOM,
                    (void *)custom, custom_len);
        *p = OSSL_PARAM_construct_end();
        if (!EVP_MAC_CTX_set_params(ctx, params))
            goto err;

        if (!EVP_MAC_init(ctx, key, key_len, params))
            /*if (!EVP_MAC_init(ctx))*/
            goto err;

        p = params;
        *p++ = OSSL_PARAM_construct_int(OSSL_MAC_PARAM_XOF, &xof_enabled);
        *p++ = OSSL_PARAM_construct_int(OSSL_MAC_PARAM_SIZE, &out_len);
        *p = OSSL_PARAM_construct_end();
        if (!EVP_MAC_CTX_set_params(ctx, params))
            goto err;

        if (!EVP_MAC_update(ctx, in, in_len))
            goto err;
        if (!EVP_MAC_final(ctx, out, &l, out_len))
            goto err;
        ret = 1;
    err:
        EVP_MAC_CTX_free(ctx);
        return ret;
    }

    int main(int argc, char *argv[])
    {

        long key_len;
        unsigned char *key = OPENSSL_hexstr2buf(argv[1], &key_len);

        long data_len;
        unsigned char *data = OPENSSL_hexstr2buf(argv[2], &data_len);

        unsigned char *custom = argv[3];
        size_t custom_len = strlen(argv[3]);

        int xof_enabled = 0;
        sscanf(argv[4], "%d", &xof_enabled);

        size_t mac_len = 32;
        sscanf(argv[5], "%d", &mac_len);

        unsigned char *mac = OPENSSL_zalloc(mac_len);

        do_kmac(data, data_len, key, key_len, custom, custom_len, xof_enabled, mac, mac_len);

        char *mac_hexstr = OPENSSL_buf2hexstr(mac, (long) mac_len);

        printf("key_hexstr: %s\ndata_hexstr: %s\ncustom: %s\nxof_enable: %d\nmac_len: %d\nkmac-128_hexstr: %s\n", 
                argv[1], argv[2], argv[3], xof_enabled, mac_len, mac_hexstr);

        OPENSSL_free(key);
        OPENSSL_free(data);
        OPENSSL_free(mac_hexstr);

        OPENSSL_free(mac);

        return 0;
    }



测试用例
***********

- `evpmac_common.txt <https://github.com/openssl/openssl/blob/master/test/recipes/30-test_evp_data/evpmac_common.txt>`_

::

    key_hexstr: 404142434445464748494A4B4C4D4E4F505152535455565758595A5B5C5D5E5F
    data_hexstr: 00010203
    custom: My Tagged Application
    xof_enable: 1
    mac_len: 32
    kmac-128_hexstr: 31a44527b4ed9f5c6101d11de6d26f0620aa5c341def41299657fe9df1a3b16c



参考资料
********

- `NIST SP 800-185 SHA-3 Derived Functions: cSHAKE, KMAC, TupleHash and ParallelHash <https://csrc.nist.gov/pubs/sp/800/185/final>`_

