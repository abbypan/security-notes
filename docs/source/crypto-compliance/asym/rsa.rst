RSA 
============



合规建议
--------

- 默认选用RSA3072，或更高强度的RSA4096等。



示例
----------------

::

    openssl genrsa -out rsa_priv.pem 3072
    openssl rsa -in rsa_priv.pem -pubout > rsa_pub.pem

    openssl rsa -pubin -text -in rsa_pub.pem

    openssl dgst -sha256 -pkeyopt rsa_padding_mode:pss -pkeyopt rsa_pss_saltlen:-1 -binary -sign rsa_priv.pem -out data.sig data.txt
    openssl dgst -sha256 -pkeyopt rsa_padding_mode:pss -pkeyopt rsa_pss_saltlen:-1 -verify rsa_pub.pem -signature data.sig data.txt

    openssl dgst -sha256 -binary data.txt > data.dgst
    openssl pkeyutl -sign -in data.dgst -inkey rsa_priv.pem -pkeyopt rsa_padding_mode:pss -pkeyopt rsa_pss_saltlen:-1 -pkeyopt digest:sha256 -out data.sig
    openssl pkeyutl -verify -pubin -inkey rsa_pub.pem -sigfile data.sig -in data.dgst -pkeyopt rsa_padding_mode:pss -pkeyopt rsa_pss_saltlen:-1 -pkeyopt digest:sha256




