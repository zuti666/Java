# Json



​	JSON 文本格式在语法上与创建 JavaScript 对象的代码相同。

由于这种相似性，无需解析器，JavaScript 程序能够使用内建的 eval() 函数，用 JSON 数据来生成原生的 JavaScript 对象。

# 格式



# 常用解析库

JSON 解析类库：

- [Gson](https://github.com/google/gson): 谷歌开发的 JSON 库，功能十分全面。
- [FastJson](https://github.com/alibaba/fastjson): 阿里巴巴开发的 JSON 库，性能十分优秀。
- [Jackson](https://github.com/FasterXML/jackson): 社区十分活跃且更新速度很快

# FastJSON对象与字符串的相互转换

| 方法                           | 作用                                 |
| :----------------------------- | :----------------------------------- |
| `JSON.parseObject()`           | 从字符串解析 JSON 对象               |
| `JSON.parseArray()`            | 从字符串解析 JSON 数组               |
| `JSON.toJSONString(obj/array)` | 将 JSON 对象或 JSON 数组转化为字符串 |

## 实例





## AJAX获取JSON文件中的数据

```java
[
 
  {
 
    "name":"张国立",
 
    "sex":"男",
 
    "email":"zhangguoli@123.com",
 
    "url":"./img/1.jpg"
 
  },
 
  {
 
    "name":"张铁林",
 
    "sex":"男",
 
    "email":"zhangtieli@123.com",
 
    "url":"./img/2.jpg"
 
  },
 
  {
 
    "name":"邓婕",
 
    "sex":"女",
 
    "email":"zhenjie@123.com",
 
    "url":"./img/3.jpg"
 
  },
 
  {
 
    "name":"张国立",
 
    "sex":"男",
 
    "email":"zhangguoli@123.com",
 
    "url":"./img/4.jpg"
 
  },
 
  {
 
    "name":"张铁林",
 
    "sex":"男",
 
    "email":"zhangtieli@123.com",
 
    "url":"./img/5.jpg"
 
  },
 
  {
 
    "name":"邓婕",
 
    "sex":"女",
 
    "email":"zhenjie@123.com",
 
    "url":"./img/6.jpg"
 
  }
 
]
```



html

```jsp
<script>
 
        //页面加载   获取全部信息
 
        $(function(){
 
            $.ajax({
 
                type: "POST",//请求方式
 
                url: "item.json",//地址，就是json文件的请求路径
 
                dataType: "json",//数据类型可以为 text xml json  script  jsonp
 
　　　　　　　　　 success: function(result){//返回的参数就是 action里面所有的有get和set方法的参数
 
                    addBox(result);
 
                }
 
            });
 
 
        });
 
        function addBox(result){
 
            //result是一个集合,所以需要先遍历
 
            $.each(result,function(index,obj){
 
                $("#box").append("<div class='product'>"+//获得图片地址
 
                    "<div><img class='img' src="+obj['url']+"/></div>"+
 
                    //获得名字
 
                    "<div class='p1 p'>"+obj['name']+"</div>"+
 
                    //获得性别
 
                    "<div class='p2 p'>"+obj['sex']+"</div>"+
 
                    //获得邮箱地址
 
                    "<div class='p3 p'>"+obj['email']+"</div>"+
 
                    "</div>");
 
            });
 
        }
 
    </script>

```

```java
package com.java.test;

import com.alibaba.fastjson.JSON;
import com.alibaba.fastjson.JSONArray;
import com.alibaba.fastjson.JSONObject;

import java.util.Arrays;
import java.util.List;

public class test {
    public static  void main(String[] args){

        //创建JSON对象
        JSONObject object = new JSONObject();
        //string
        object.put("string","王靖");
        //int
        object.put("int",2);
        //boolean
        object.put("boolean",true);
        //array
        List<Integer> integers = Arrays.asList(1,2,3);
        object.put("list",integers);
        //null
        object.put("null",null);

        System.out.println(object);

     //JSON对象到Java变量
        //string
        String s = object.getString("string");
        System.out.println(s);
        //int
        int i = object.getIntValue("int");
        System.out.println(i);
        //boolean
        boolean b = object.getBooleanValue("boolean");
        System.out.println(b);
        //list
        List<Integer> integers2 = JSON.parseArray(object.getJSONArray("list").toJSONString(),Integer.class);
        integers2.forEach(System.out::print);


        //相互转换
        //从字符串解析JSON对象
        JSONObject obj = JSON.parseObject("{\"runoob\":\"菜鸟教程\"}");
        System.out.println(obj);
        //将JSON对象转化为字符串
        String objStr = JSON.toJSONString(obj);
        System.out.println(objStr);

        //从字符串解析JSON数组
        JSONArray arr = JSON.parseArray("[\"菜鸟教程\",\"RUNOOB\"]\n");
        System.out.println(arr);

        //将JSON数组转化为字符串
        String arrStr = JSON.toJSONString(arr);
        System.out.println(arrStr);

        String u = "{\"results\":[{\"location\":{\"id\":\"WX4FBXXFKE4F\",\"name\":\"北京\",\"country\":\"CN\",\"path\":\"北京,北京,中国\",\"timezone\":\"Asia/Shanghai\",\"timezone_offset\":\"+08:00\"},\"now\":{\"text\":\"晴\",\"code\":\"0\",\"temperature\":\"13\"},\"last_update\":\"2020-10-22T10:00:00+08:00\"}]}";
        JSONObject jsonObject = JSON.parseObject(u);
        JSONArray results = jsonObject.getJSONArray("results");                //得到键为results的JSONArray
        System.out.println(results);

        JSONObject result1 = results.getJSONObject(0);   //得到results数组第一个数据中键为location的JSONObject
        System.out.println(result1);

        JSONObject now = result1.getJSONObject("now");
        System.out.println(now);

        String code = now.getString("code");
        System.out.println(code);

        JSONObject location = result1.getJSONObject("location");
        System.out.println(location);

        String lastupdate = result1.getString("last_update");
        System.out.println(lastupdate);


    }

}

```

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201022113754.png)