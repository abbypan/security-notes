防重放(Anti Replay)
=======================


timestamp/counter
------------------

timestamp/counter 单调递增。

1. 发送方使用当前 timestamp，或 counter+1 。
#. 发送方对 { sender_id, data, timestamp/counter } 计算数字签名sig/消息认证码mac。
#. 发送方发送 { sender_id, data, timestamp/counter, sig/mac }。
#. 接收方校验sig/mac。
#. 接收方检查收到timestamp/counter是否高于已记录的timestamp/counter，即，timestamp > record_timestamp, 或 counter > record_counter。
#. 检查通过，接收方记录新的timestamp/counter，接收方接受data。


challenge
------------------

1. 发送方向接放方请求challenge。
#. 发送方对 { sender_id, data, challenge } 计算数字签名sig/消息认证码mac。
#. 发送方发送 { sender_id, data, challenge, sig/mac }。
#. 接收方校验sig/mac。
#. 接收方检查收到challenge是否与自身发出的challenge相符。
#. 如果相符，接收方接受data。


合规建议
--------

- 时延敏感的业务可选择timestamp/counter的防重放方案。
- 高风险业务应选择challenge，或timestamp/counter + challenge的防重放方案。
