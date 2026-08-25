Roughtime
############

`Roughtime: Securing Time with Digital Signatures <https://blog.cloudflare.com/roughtime/>`_

client先发一个nonce。

server端回复timestamp+radius，并且打签名的时候把nonce带上。

server端的public key合法性可以由上一级的delegator签名来校验。

避免nts的bootstrap问题。
