Noise
===========================

- Initiator和Responder均无Long-term Keypair，选用Noise-NN。
- Initiator已知Responder的Long-term Public Key, Initiator无Long-term Keypair，选用Noise-NK。
- Initiator和Responder己知对方的Long-term Public Key，选用Noise-KK。
- Initiator已知Responder的Long-term Public Key, Initiator临时传输自身的Long-term Public Key，选用Noise-XK。
- Initiator和Responder互相传输自身的Long-term Public Key给对方，选用Noise-XX。 


合规建议
--------

- Long-term Public Key必须进行公钥安全检查。
- Long-term Public Key如果以证书(例如X.509 Certificate)形式给出，必须进行证书安全检查，同时检查证书内容与通信方身份是否匹配。


参考资料
--------

- `Noise Protocol Framework <https://noiseprotocol.org/>`_
