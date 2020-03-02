## ***[20180123]*** MySQL
> #### 小技巧：
>> ***[20180123]*** 中文按首字母排序
>>>
   - 使用 CONVERT(field_name USING gbk) 函数将指定字段转码成gbk；
   - 例子：
    - ```SELECT * FROM table_name ORDER BY CONVERT(field_name USING gbk) ASC LIMIT 10;```

>> ***[20180205]*** 拼接(连接字符串)
>>>
   - 使用 CONCAT(str...);
   - 例子:
    - ```SELECT id,name,CONCAT(id,'-',name) as truename FROM test_user;```
   - 更新：为已有数据拼接其他字符时更好用，例如为图片相对路径拼接成绝对路径。

>> ***[20180206]*** 排序、区间搜索
>>>
   - 字段类型慎用```varchar```;
   - ```varchar```是按字典序来排序, 例如1，2，10的排序是1，10，2。

> #### 错误码
>> ***[20180206]*** 3065
>>> 
   - Mysql 5.7版本默认开启严格模式,
   - 该错误码是DISTINCT与order by一起使用造成的；
   - 严格模式关闭ONLY_FULL_GROUP_BY.

> #### 修复
>> ***[20180217]*** 丢失performance_schema.session表
>>> ```mysql_ugrade -u root -p --force```