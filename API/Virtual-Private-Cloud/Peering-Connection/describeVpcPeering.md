# describeVpcPeering


## 描述
查询VpcPeering资源详情

## 请求方式
GET

## 请求地址
https://vpc.jdcloud-api.com/v1/regions/{regionId}/vpcPeerings/{vpcPeeringId}

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|True| |Region ID|
|**vpcPeeringId**|String|True| |vpcPeeringId ID|

## 请求参数
无


## 返回参数
|名称|类型|描述|
|---|---|---|
|**result**|[Result](describeVpcPeering#user-content-result)|返回结果|
|**requestId**|String|请求ID|

### <div id="Result">user-content-result</div>
|名称|类型|描述|
|---|---|---|
|**vpcPeering**|[VpcPeering](describeVpcPeering#user-content-vpcpeering)|VpcPeering资源信息|
### <div id="user-content-vpcpeering">VpcPeering</div>
|名称|类型|描述|
|---|---|---|
|**vpcPeeringId**|String|VpcPeering的Id|
|**vpcPeeringName**|String|VpcPeering名称，同账号下不允许重名，取值范围：1-32个中文、英文大小写的字母、数字和下划线分隔符|
|**vpcPeeringState**|String|状态，取值为Connected，Disconnected，Initiated|
|**description**|String|VpcPeering 描述，可为空值，取值范围：0-256个中文、英文大小写的字母、数字和下划线分隔符|
|**vpcInfo**|[VpcPeeringVpcInfo](describeVpcPeering#user-content-vpcpeeringvpcinfo)|发起VpcPeering的Vpc信息|
|**remoteVpcInfo**|[VpcPeeringVpcInfo](describeVpcPeering#user-content-vpcpeeringvpcinfo)|对端的Vpc信息|
|**createdTime**|String|VpcPeering创建时间|
### <div id="user-content-vpcpeeringvpcinfo">VpcPeeringVpcInfo</div>
|名称|类型|描述|
|---|---|---|
|**vpcId**|String|子网所属VPC的Id|
|**vpcName**|String|私有网络名称，取值范围：1-60个中文、英文大小写的字母、数字和下划线分隔符|
|**addressPrefix**|String[]|如果为空，则不限制网段，如果不为空，10.0.0.0/8、172.16.0.0/12和192.168.0.0/16及它们包含的子网，且子网掩码长度为16-28之间|

## 返回码
|返回码|描述|
|---|---|
|**200**|OK|

## 请求示例
调用方法、签名算法及公共请求参数请参考[京东云OpenAPI公共说明](https://docs.jdcloud.com/common-declaration/api/introduction)。
- 请求示例: 查询id为vpcpr-qrn8hp2btw的vpcPeering信息

GET
```
/v1/regions/cn-north-1/vpcPeerings/vpcpr-qrn8hp2btw

```

## 返回示例
```
{
    "requestId": "4960c971-cab1-40ce-b3c8-72d85a6408c9", 
    "result": {
        "vpcPeering": {
            "createdTime": "2021-08-09T05:16:00Z", 
            "description": "11222", 
            "remoteVpcInfo": {
                "addressPrefix": [
                    "10.0.0.0/16", 
                    "2403:1ec0:b500:1500::/56"
                ], 
                "vpcId": "vpc-twvlqso4g0", 
                "vpcName": "v6-1"
            }, 
            "vpcInfo": {
                "addressPrefix": [
                    "10.128.0.0/25", 
                    "2403:1ec0:b500:1d00::/56"
                ], 
                "vpcId": "vpc-5056ovs7t5", 
                "vpcName": "ipv6"
            }, 
            "vpcPeeringId": "vpcpr-qrn8hp2btw", 
            "vpcPeeringName": "zcx-test", 
            "vpcPeeringState": "Initiated"
        }
    }
}
```
