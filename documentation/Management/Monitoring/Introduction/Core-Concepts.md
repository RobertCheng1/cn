# 核心概念
## 监控类
**监控指标**  
指标是云监控中的基本概念。指标表示一个发布到云监控并且按时间排序的数据点集。可将指标视为要监控的变量，而数据点代表该变量随时间变化的值。例如，特定云主机实例的 CPU 使用率是京东云主机提供的一个指标。数据点本身可来自于您从中收集数据的任何应用程序或业务活动。
云服务资源将指标发送给云监控。您可以按一组有序的时间序列数据来检索关于这些数据点的统计数据。

**统计数据**   
统计数据是指定时间段内的指标数据聚合。所有统计数据都有度量单位。常见单位包括 秒（时间单位）、Byte（字节）、bit（比特）、%（百分比）和次（计数单位）。

**时间段**   
时间段是云监控统计数据的间隔时间长度，每个时间戳数据代表在指定时间段内对收集的所有数据进行聚合的结果。时间段的最小粒度为一分钟。

**时间戳**  
在云监控中每个指标数据点必须有一个时间标记，表示此原始数据采集的时间。在请求中使用的时间戳必须为 dateTime 对象，并包含完整的日期及小时、分钟和秒，例如：2000-01-31 23:59:59，建议您以北京时间（东八时区）提供时间戳。

**指标数据聚合**  
云监控将根据您在检索统计数据时指定的监控周期长度聚合统计数据。  
如选择1小时的监控周期时，最小粒度为1分钟，即每个数据点是由一分钟内对收集的所有数据进行聚合的结果。不同监控周期，其聚合最小粒度如下：

监控周期| 最小粒度
---|---
1小时 | 1分钟
6小时 | 5分钟
12小时 | 10分钟
1天 | 20分钟
3天 | 1小时
7天 | 2小时
1个月 | 3小时

**监控周期**   
指云监控中某一指标的监控时间周期，可自选时间段：最多支持自当天起往前一个月长度的监控周期。可自选周期范围：1小时、6小时、12小时、1天、3天、7天、14天、自选时间段。

**云监控状态**  
正常：当前资源运行正常，指标数据未达到所设报警标准。  
报警：当前资源指标数据已达到所设报警标准。  
数据不足：暂未获取到当前资源监测数据。  
未设置：当前资源未设置报警规则。  
未启用：当前资源已设置报警但未启用。

**数据对比**  
是指用户可以根据业务需求将任意两个时间跨度相同的时间段内的资源的见监控数据进行对比。

**视图维度**  
是指监控数据在图表中的展示方式，包括明细和汇总两个维度。  
明细：多个实例相同指标不做聚合处理，一个资源的一个监控项展示一条数据。
汇总：多个实例相同的指标汇总展示，一个监控项展示一条数据。

## 报警类
**报警**  
使用报警可在指定的时间段内监控单个指标，并根据指标值相对于阈值的变化情况执行一项或多项指定操作。根据您设置的报警规则，当资源达到阈值时，会第一时间通过短信、邮件方式告知您，为您的业务保驾护航。

**报警统计周期**  
报警系统会按照这个周期检查您对应的监控数据是否超过了报警阈值。例如设置内存使用率报警规则的统计周期为1分钟，则每间隔1分钟会检查一次内存使用率是否超过了阈值。

**统计方法**  
统计（Statistic）是将指定时间段(Period)内的监控项数据进行聚合。目前提供的统计方法包括平均值、最大值、最小值、求和值。

**平均值**  
统计周期内监控数据的平均值。统计结果是15分钟内采集的所有监控数据的平均值，当这个平均值大于80%时，才算超过阈值。

**最大值**  
统计周期内监控数据的最大值。统计周期内采集的监控数据中，最大值超过80%，即为超过阈值。

**最小值**  
统计周期内监控数据的最小值。统计周期内采集的监控数据中，最小值超过80%，即为超过阈值。

**持续周期**  
连续几次超过阈值后报警：指连续几个统计周期监控项的值持续超过阈值后触发报警。  
例如：设置 CPU 使用率超过 80% 报警，统计周期为5分钟，连续 3 次超过阈值后报警，则第一次探测 CPU 使用率超过 80% 时，不会发出报警通知。5 分钟后第二次探测 CPU 使用率超过 80%，也不会发出报警。第三次探测仍然超过 80% 时，才会发出报警通知。即从实际数据第一次超过阈值到最终发出报警规则，最少需要消耗的时间为统计周期(连续探测次数-1)=5(3-1)=10分钟。
