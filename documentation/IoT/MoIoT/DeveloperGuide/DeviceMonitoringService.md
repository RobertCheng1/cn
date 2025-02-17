# 设备监控服务

**商业物联管理系统设备监控服务可针对单台（或批量）设备配置监控项和监控项报警阈值，当出现监控项触发监控事件后，可根据相应事件响应配置执行相应处理动作。**

## 可配置监控项
目前平台提供以下两类监控项：
1) 操作日志监控
 - 可对敏感操作指令及其执行结果进行监控。

2) 设备运行时数据监控
 - 设备配置数据：可对配置数据变更进行监控；
 - 设备行为记录：可对设备上下线、设备开关机、应用安装、应用启动、应用停止、应用崩溃、应用卸载、定位位置变更等设备行为进行监控；
 - 设备OS快照数据：可对内存、CPU等使用情况、网络稳定情况、网络流量使用数据等数据进行监控；
 - 截屏图片数据：可对截屏图片进行分析，实现敏感内容监控，以及对黑屏、崩溃等异常情况进行监控；

4) 应用运行数据监控
 - 应用使用率监控：应用在前台运行的时长；
 - 应用响应时间及相应速度监控——需要应用提供日志；
 - 应用占用内存资源监控；
 - 应用占用CPU资源监控；
 - 应用消耗流量数据监控；

## 监控事件处理动作
1)	报表或日志提醒；
2)	邮件、短信、电话提醒；
3)	关闭、重启设备操作；
4)	启动、停止应用操作；

## 监控服务配置方式
1)	选择符合业务场景的监控模板进行快捷配置；
2)	自定义配置，可增加删除监控项、可调整监控阈值、可选择监控事件处理动作；




