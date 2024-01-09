| 路由路径            | 获取数据方法                                                 | 匹配的url格式                          | 方法得到的值                     | 备注                         |
| ------------------- | ------------------------------------------------------------ | -------------------------------------- | -------------------------------- | ---------------------------- |
| GET `参数在url中`   |                                                              |                                        |                                  |                              |
| /:name              | c.Param("name")                                              | /`john`                                | john                             |                              |
| /:name/*action      | c.Param("action")                                            | /john`/`                               | /                                |                              |
|                     |                                                              | /john                                  | /                                | 没有对应路由时重定向到/john/ |
|                     |                                                              | /john`/send`                           | /send                            |                              |
| /welcome            | c.DefaultQuery("firstname", "Guest") <br> c.Query("lastname") | /welcome                               | firstname:Guest <br> lastname:   |                              |
|                     |                                                              | /welcome`?firstname=Jane&lastname=Doe` | firstname:Jane <br> lastname:Doe |                              |
| POST `参数在body中` |                                                              |                                        |                                  |                              |
| /form_post          | c.PostForm("message") <br> c.DefaultPostForm("message","anonymous") | /form_post <br> `参数在body,form-data` | body,form-data中的值             |                              |
| /upload             | c.FormFile("filename")                                       | /upload <br> `文件在body,form-data`    | body,form-data中的文件           |                              |
| /uploadfiles        |                                                              | /uploadfiles                           |                                  |                              |


| 模型绑定函数          | GET,: | GET,? | POST,Params | POST,body |                                        |
|-----------------|-------|-------|-------------|-----------|----------------------------------------|
| ShouldBind      |       | √     | √           | ×         | 绑定post params,同时绑定get post参数,绑定HTML复选框 |
| ShouldBindJSON  |       |       | ×           | √         |                                        |
| ShouldBindXML   |       |       | ×           | √         |                                        |
| ShouldBindWith  |       | √     |             |           | 自定义验证器                                 |
| ShouldBindQuery |       | √     | ---------   | --------- |                                        |
| ShouldBindUri   | √     |       |             |           |                                        |







