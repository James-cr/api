# 获取网络ACL的绑定关系列表-DescribeNetworkAclAssociation

获取网络ACL的绑定关系列表

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|AclId|string|Acl的ID|**Yes**|
|Offset|int|列表偏移量|No|
|Limit|string|列表获取的个数限制|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|AssociationList|array|绑定信息列表|**Yes**|

## AssociationInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|AssociationId|string|绑定ID|**Yes**|
|VpcId|string|所属的VPC ID|**Yes**|
|AclId|string|ACL的ID|**Yes**|
|SubnetworkId|string|绑定的子网ID|**Yes**|
|CreateTime|int|创建的Unix时间戳|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeNetworkAclAssociation
&Region=cn-bj
&ProjectId=org-xxxxx
&AclId=netacl-xxxxxx
&Offset=6
&Limit=5
```

# Response Example
```
{
    "Action": "DescribeNetworkAclAssociationResponse", 
    "TotalCount": 1, 
    "AssociationList": [
        {
            "AssociationId": "netaclassoc_xxxxxx", 
            "SubnetworkId": "subnet-xxxxxx", 
            "CreateTime": 1583374605, 
            "AclId": "netacl-xxxxxx"
        }
    ], 
    "RetCode": 0
}
```

