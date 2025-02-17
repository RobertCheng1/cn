# 创建集群

您可以在云搜索Elasticsearch控制台新建集群，关于实例的计费说明请参见“[价格总览](../Pricing/Price-Overview.md)”、“[计费规则](../Pricing/Billing-Rules.md)”。

## 前提条件

- 已注册京东云账号，并完成实名认证。如果还没有账号请 [注册](https://accounts.jdcloud.com/p/regPage?source=jdcloud&ReturnUrl=https%3a%2f%2fuc.jdcloud.com%2fpassport%2fcomplete%3freturnUrl%3dhttps%3a%2f%2fwww.jdcloud.com)，或 [实名认证](https://uc.jdcloud.com/account/certify)。
- 如计费类型选择按配置计费，请确认您的账户余额（包括代金券）能满足您的使用。

## 操作步骤

1. 登录[云搜索Elasticsearch 控制台](https://es-console.jdcloud.com/clusters)。

1. 在实例列表页面单击**创建**，进入“创建集群”页面。

1. 进入“创建集群”页面后，可设置地域、基本信息、规格、网络、快照等信息。

   - **地域**：目前支持“华北-北京”、“华南-广州”、“华东-上海”。

   - **可用区**：可用区是使用独立电源和网络资源的物理区域。通过内部网络互联，再以物理方式进行隔离，提高了应用程序的可用性。
   - **部署方式**：支持单可用区和多可用区部署。单可用区部署支持跨机架容灾，多可用区部署支持跨机房容灾，但网络会有一定延迟，可根据业务要求选择。选择多可用区部署时，集群的数据节点会均匀的分布到您选择的多个多用区中，所部署的数据节点支持可用区感知功能，可使数据的副本分布到多个可用区中，保证单个可用区仅有一份副本，当单个可用区出现故障时，剩余可用区仍然可以不间断的提供服务。
   - 单可用区部署支持跨机架容灾，多可用区部署支持跨机房容灾，但网络会有一定延迟。

   - **版本**：当前支持5.6.9、6.5.4、6.7.0、6.8.13、7.5.2、7.9.3。

   - **集群名称**：自定义的集群名称，名称不可为空，只支持数字、大小写字母、英文下划线“_”及中划线“-”，以字母开头且不能超过32字符。

   - **存储类型**：支持本地SSD盘、性能型SSD云盘、容量型HDD云盘。

   - **节点规格**：支持多种计算规格，可以根据具体业务情况选择。

   - **单点存储规格**：存储规格范围20-16000GB，步长为10GB，可输入整数。

   - **节点数量**：支持工单方式提升节点配额。

   - **启用专有主节点**：专用主节点的使用可以提高集群稳定性，建议开启专用主节点，开启后可选择节点规格和数量。
   - **启用协调节点**：协调节点就像负载均衡器一样，用来响应客户请求，均衡每个节点的负载。协调节点的加入可以释放数据节点承担的均衡节点负载的任务，使大型集群受益。开启后可选择节点规格和数量。

   - **私有网络**： 显示当前VPC列表，默认选择最新创建的VPC。单击列表后“新建私有网络”跳转至私有网络（VPC）页面。

   - **子网**： 显示当前子网列表，默认选择最新创建的子网。单击列表后“新建子网”跳转至私有网络-子网页面。

   - **快照**： 默认关闭，可开启，开启后可选择每天备份时间。
   - 购买量：计费方式选择包年包月时需选择购买时长和是否自动续费。

4. 单击“立即购买”，完成购买流程。
5. 创建的集群将展现在集群列表中，状态为“创建中”，耐心等待几分钟，创建成功后集群状态会变为“运行”。

 
