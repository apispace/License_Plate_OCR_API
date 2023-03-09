# APISpace 介绍
**本 API 服务由 [APISpace（apispace.com）](https://www.apispace.com/?utm_source=github&utm_term=chepaiocr) 提供。**

APISpace 是 Eolink 旗下专业的 API 开放与交易平台，为广大企业以及个人开发者提供多维度、全方位的API接口，覆盖短信验证、天气查询、快递物流、OCR文字识别等海量 API 服务，帮助用户快速获取数据，降低获取数据的成本和难度，提升开发效率。

APISpace 提供15种开发语言的代码示例，分别是：
- Java(OK HTTP)
- HTTP
- cURL
- 微信小程序
- PHP(pecl_http)、PHP(cURL)
- Python(http.client)、Python(Requests)
- JavaScript(Jquery AJAX)、JavaScript(XHR)
- NodeJS(Native)、NodeJS(Request)
- Ruby(Net:Http)
- Shell(Httpie)、Shell(cUrl)

# 车牌识别OCR
支持12种中文车牌类型，如蓝牌、黄牌（单双行）、绿牌、大型新能源（黄绿)，并能同时识别图像中的多张车牌。

**使用该产品前，您需要通过 [https://www.apispace.com/eolink/api/lisence-recognition/introduction](https://www.apispace.com/eolink/api/lisence-recognition/introduction?utm_source=github&utm_term=chepaiocr) 申请API服务**

本文档末尾提供了 Python(Requests) 的调用代码示例，可以前往文档末尾查看。

更多代码示例：[https://www.apispace.com/eolink/api/lisence-recognition/guidence/](https://www.apispace.com/eolink/api/lisence-recognition/guidence/?utm_source=github&utm_term=chepaiocr)

### 车牌类型

识别中国大陆各类机动车车牌信息，支持12种中文车牌类型：

1.  单行蓝牌
1.  单行黄牌
1.  新能源车牌
1.  白色警用车牌
1.  教练车牌
1.  武警车牌
1.  双层黄牌
1.  双层武警
1.  使馆车牌
1.  港澳牌车
1.  双层农用车牌
1.  民航车牌


### 应用场景

1.  #### **车辆进出场识别**

自动识别车辆车牌信息，应用于停车场、小区、工厂等场景，实现无卡、无人的车辆进出场自动化、规范化管理，有效降低人力成本和通行卡证制作成本，大幅度提升管理效率。


2.  #### **道路违章检测**

自动识别定位违章车辆信息，实时检测记录道路违章行为，有效降低人力监控成本，提升管理效率。 


### 识别效果

```
{
    "result": [{
        "rect": [622, 825, 1231, 1008],
        "landmarks": [
            [622, 824],
            [1238, 820],
            [1238, 1009],
            [620, 1014]
        ],
        "number": "沪KR9888",
        "roi_height": 190,
        "confidence": 0.84,
        "class": "single"
    }],
    "count": 1,
    "log_id": "41cfc2b0-bd9b-11ed-9724-0000000032d8"
}
```

### 服务保障
![image](https://user-images.githubusercontent.com/36323798/223978485-7b70f644-a69f-4c21-ab4c-d16abd65f06e.png)

### Python(Requests) 调用代码示例

```
import requests

url = "https://eolink.o.apispace.com/lisence-recognition/api/v1/lisence-recognition"

payload = {"image":"","url":"https://n.sinaimg.cn/sinacn/20171023/72b6-fymzzpv9860803.jpg"}

headers = {
    "X-APISpace-Token":"",
    "Authorization-Type":"apikey",
    "Content-Type":"application/json"
}

response=requests.request("POST", url, data=json.dumps(payload), headers=headers)

print(response.text)

```
