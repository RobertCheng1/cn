# FAQ
## 目前云数据库支持的类型
云数据库 RDS 支持以下引擎及版本，后续将会支持更多的数据库引擎类型和版本

- MySQL
    - 5.5
    - 5.6
    - 5.7
    - 8.0
  
- Percona:
    - 5.7
  
- MariaDB
    - 10.2
    
- PostgreSQL
    - 9.6
    - 10
    - 11
    - 12
    - 13

- SQL Sever
    - 2008 R2：企业版
    - 2012：企业版、标准版
    - 2014：企业版、标准版
    - 2016：企业版、标准版、Web版
    - 2017：企业版

## 云主机无法访问 RDS
云主机要访问 RDS，必须满足以下几个条件：
  - 云主机必须和 RDS 在同一个 VPC 中。
  - 如果用户在云主机中配置的安全组规则不正确，也会导致从云主机中无法访问数据库。正确的配置云主机安全组的方法可查看云主机相关设置。

## 软件许可
- 云数据库 SQL Server 已经包含了微软SQL Server软件许可，实例创建后即具有微软SQL Server许可授权。您无需再单独购买SQL Server许可。
- 当购买SQL Server实例过期并删除后，对应的软件许可也随之失效，您不能将原有的许可授权用于其他地方。
- 京东云的云数据库SQL Server暂不支持用户自带SQL Server许可。

## 实例重启后，云数据库 SQL Server 性能分析中看不到历史数据了
性能分析中的数据是保存在实例内存中。实例重启后，性能分析数据将丢失。 如果您有对历史数据分析的需求，可以使用以下两个OpenAPI将数据导出保存
- describeIndexPerformance
- describeQueryPerformance

## 开通了实例外网访问后，但还是无法通过外网连接到云数据库 RDS 实例
为保障数据安全，云数据库 RDS 的白名单缺省只对本实例所在的VPC开放。因此您还需要在白名单中添加您外网的 IP 地址，才能访问该数据库实例。

## 根据备份或时间点创建数据库时，为什么不用输入用户名和密码
根据备份或时间点创建的新数据库会沿用备份源数据库的用户名和密码，暂不支持创建时用户手动输入。

## 根据备份创建时，为什么我的可选配置显示只显示一部分
用户在根据备份创建时，只能选择不小于当前备份实际大小的配置。

## 现在自动备份的保存多少天啊
目前自动备份至少为您保留7天。

## 京东云云数据库 RDS 实例长时间处于创建中状态，怎么解决
京东云云数据库 RDS 创建时候所选择的子网如果设置了网络ACL，请确保出站规则增加了类型为 DNS（UDP）的规则，并且设置为了接受，由于网络ACL是无状态的，请确保入站规则也进行了允许 ALL UDP 类型配置。如果问题还是没有解决，请工单联系客服。

## 如何修改云数据库 MySQL 实例参数
目前京东云暂不支持用户自定义修改云数据库 MySQL 实例参数，您可以通过提交工单的方式将您的需求反馈给京东云的工程师，由工程师协助您进行修改。

## 针对云数据库 MySQL 中的一个大表，删除了一些数据，但是通过监控图，数据空间磁盘占用并未发生变化
这是数据文件碎片空洞问题。在 InnoDB 执行删除数据时，已经删除的空间并不会回收，会造成很多文件空洞，导致监控图中的数据空间使用量并不会发生变化。优化方法：`OPTIMIZE TABLE <table>` 或者 `ALTER TABLE <table> ENGINE=Innodb` 来重建表空间。

## 我创建了库，但是我想修改库的字符集，我的账号没有权限，并且控制台也没有相应的入口，怎么办？
如果需要修改库的字符集, 可以通过 DMS 来进行相关操作；点击控制台登录数据库，成功登录 DMS 后，左侧选中你要修改字符集的库名，然后再点击后测顶栏的操作tab，会刷新当前页面，然后可以看到当前页面有一个排序规则选项，选择你想要修改的字符集，然后点击执行按钮即可。

## 我希望可以在 MySQL 中存储表情相关内容，需要将 character_set_server 设置为 utf8mb4, 是不是只能提工单解决？
其实 character_set_server 参数的主要作用是通过命令行创建库的时候未指定字符集的情况下，默认会根据 character_set_server 的值来创建；但是京东云云数据库 MySQL 创建库的操作默认只能通过控制台来操作，并且是可以指定字符集为 utf8mb4。有些用户可能会发现即使这样操作了，通过客户端工具连接数据库实例时候看到的数据是乱码的，所以认为是因为 character_set_server 未设置为 utf8mb4 导致的，其实并非如此，这块还涉及到 character_set_client，character_set_connection，character_set_result 等相关字段的设置，***然后这些字段其实是客户端可以手动指定的***，具体可参见官网文档：[Connection Character Sets and Collations](https://dev.mysql.com/doc/refman/5.7/en/charset-connection.html)

## 我通过 SQL 语句查询 MySQL 数据库占用的空间比监控的硬盘空间总使用量小 
如果您想看数据库实例的本地磁盘占用空间，请以监控里面的硬盘空间总使用量为准，通过 SQL 命令查询的数据库占用空间，由于 MySQL 中的 information_schema.tables 表信息并非是实时更新的，所以统计的结果会不准确的。

## 如何在 RDS 的控制台中如何导出 MySQL的数据
为了安全，目前暂不支持通过控制台导出 MySQL 数据库中的数据。 如果有导出数据的需求，可以通过mysqldump 命令进行。
