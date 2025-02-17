# 限制说明

只有成功申请了公网IP的京东云用户，才有权限使用基础防护功能。

## 防护带宽

基础防护攻击防护能力与您所购买公网IP的带宽有关, 如果公网IP受到的攻击超过了该IP的黑洞阈值，则会触发黑洞，屏蔽其所有的访问。公网IP的黑洞阈值与带宽的对应关系如下表所示。

|     带宽（Mbps)     | 黑洞阈值 |
| :-----------------: | :------: |
|     带宽 <= 100     |    2G    |
|  100 < 带宽 <= 200  |    2G    |
|  200 < 带宽 <= 500  |    2G    |
| 500 < 带宽 <= 1000  |    3G    |
| 1000 < 带宽 <= 2000 |    4G    |
| 2000 < 带宽 <= 5000 | 带宽值*2 |
|     带宽 > 5000     | 带宽值*2 |


如果您需要更高的攻击防护能力，请购买DDoS防护包。

购买防护包后，黑洞阈值即为DDoS防护包保底+弹性总带宽值。


## 相关参考
- [DDoS防护包介绍](https://www.jdcloud.com/cn/products/anti-ddos-protection-package)
