[Работа с вложениями](../../index.md)
=====================================================

### ![POST](../../../../img/get.png) [/attachment/create](../index.md)

### Examples

**URI** `http://tempurl.com/attachment/create HTTP/1.1`

**Request**
```json
{
    "attachment":{
        "meta":{
            "name":"проверка.txt",
            "type":"text/plain"
        },
        "data":"0KLQtdC60YHRgtC+0LLRi9C5INGE0LDQudC7"
    }
}
```

**Response**
```json
{
    "result":[
        {
            "id":"#1586:412",
            "digest":"6e4a3290ff2ab22fed4e747c95678bbf534b41d0",
            "name":"проверка.txt",
            "type":"text/plain",
            "size":27,
            "created":"2018-10-02 18:53:06"
        }
    ]
}
```