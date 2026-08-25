说明
====

证书格式例如：X.509, C.509 等。


示例
------------------

::

    openssl x509 -in test_cert.pem -pubkey -noout > test_pub.pem

    openssl req -new -key test_priv.pem -out test_cert_req.csr -subj "/C=CN/ST=AH/L=HF/O=XXX/OU=YYY/CN=ZZZ"
