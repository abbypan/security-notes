MTE
==============

ARMv8.5-A MTE

https://developer.arm.com/-/media/Arm%20Developer%20Community/PDF/Arm_Memory_Tagging_Extension_Whitepaper.pdf

Memory tagging: 以4-bits tag覆盖16 bytes memory计算，cost折扣3.125%。




Apple MIE(Memory Integrity Enforcement)
------------------------------------------

https://security.apple.com/blog/memory-integrity-enforcement/

A19

以Enhanced Memory Tagging Extension (EMTE) 为基础

系统组件强制开启 Always-on system-wide

类型隔离 Type-aware allocators

memory free后强制retag, 避免UAF

Tag强保护，避免泄露 confidentiality
