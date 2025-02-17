#  对象存储类型介绍
OSS提供标准存储、低频存储、归档存储、低冗余存储四种存储类型，全面覆盖从热到冷的各种数据存储场景。

**说明**：各存储类型的定价信息请参见[价格总览](https://docs.jdcloud.com/cn/object-storage-service/price-overview),具体的计费方式请参见[计费规则](https://docs.jdcloud.com/cn/object-storage-service/billing-rules)。

* [标准存储](StorageClass-Overview#user-content-1)
* [低频存储](StorageClass-Overview#user-content-2)
* [归档存储](StorageClass-Overview#user-content-3)
* [低冗余存储](StorageClass-Overview#user-content-4)


### 标准存储（STANDARD）

<div id="user-content-1"></div>
为用户提供了高可靠性、高可用性、高性能的对象存储服务，能够支持频繁的数据访问。标准存储拥有低访问时延与高吞吐量，因而适用于有大量热点文件。标准存储类型是各种社交、分享类的图片、大型网站、音视频应用、大数据分析的合适选择。

### 低频存储（STANDARD-IA）

<div id="user-content-2"></div>
OSS低频存储类型适合长期保存不经常访问的数据（平均每月访问频率1到2次）。存储单价低于标准类型，适合各类移动应用、智能设备、企业数据的长期备份，支持实时数据访问。低频访问存储类型的Object有最短存储时间，存储时间短于30天的Object提前被删除会产生一定费用。低频访问存储Object有最小计量空间，Object大小低于64KB，会按照64KB计算存储空间，数据获取会产生费用。

### 归档存储（GLACIER）

<div id="user-content-3"></div>
OSS归档存储类型在存储类型中单价最低，适合需要长期保存（建议半年以上）的归档数据，在数据的存储周期内极少被访问；数据取回时，需要根据您选择的取回模式，等待几分钟到几小时。归档存储类型适合需要长期保存的档案数据、操作日志、影视素材等。归档存储类型的Object有最短存储时间，存储时间短于60天的Object提前删除会产生一定费用。归档类型存储Object有最小计量空间，Object大小低于48KB，会按照48KB计算存储空间，数据获取会产生数据取回费用。


### 低冗余存储（REDUCED_REDUNDANCY）

<div id="user-content-4"></div>
OSS低冗余存储类型需要用户能够承受数据丢失，不推荐使用。



### 存储类型对比

| 对比项        | 标准存储                                               | 低频存储                             | 归档存储                               |
| ------------- | ------------------------------------------------------ | ------------------------------------ | -------------------------------------- |
| 数据持久性    | 99.999999999%                                          | 99.999999999%                        | 99.999999999%                          |
| 服务可用性    | 99.995%                                                  | 99.9%                                | 99.0%                                  |
| 数据访问延时  | 实时访问ms级延迟                                       | 实时访问ms级延迟                     | 需提前申请恢复                         |
| 图片处理      | 支持                                                   | 支持                                 | 取回后支持                             |
| 音视频处理    | 支持                                                   | 支持                                 | 取回后支持                             |
| 支持地域      | 全部地域                                               | 全部地域                             | 全部地域                               |
| HTTPS加密传输 | 支持                                                   | 支持                                 | 支持                                   |
| 存储费用      | 标准                                                   | 较低                                 | 极低                                   |
| 数据取回费用  | 免费                                                   | 较低                                 | 较高                                   |
| 最小计量空间  | 无                                                     | 64KB                                 | 48KB                                   |
| 最短存储时间  | 无                                                     | 30天                                 | 60天                                   |
| 读写请求费用  | 极低                                                   | 较低                                 | 较低                                   |
| 适应场景      | 音视频分发源站、图片分享、大型网站 | 网盘存储、政企数据备份、监控数据存储 | 医疗影像、档案数据、业务日志、影像素材 |

