AMD-SNP
===========


Heracles
------------

https://heracles-attack.github.io/

Chosen Plaintext Attack on AMD SEV-SNP

在VM生命周期内，memory encryption key不变，AES-XEX 模式， tweak 用的 memory address（不变）

hypervisor 可以 move page

反复尝试move page，观察密文变化，即可 brute force
