
下面的mybatis查询

```xml
<select id="selectUserById" resultType="com.itqiankun.mybatis.source.entity.User"
            parameterType="java.lang.Integer">
        select * from user where id = #{id}
    </select>
```

调用如下

```java
User user = mapper.selectUserById(1);
```

debug对应`BoundSql`对象的json字符串

```json
{
  "parameterMappings": [
    {
      "javaType": "java.lang.Integer",
      "mode": "IN",
      "property": "id",
      "typeHandler": {
        "rawType": "java.lang.Integer"
      }
    }
  ],
  "parameterObject": 1,
  "sql": "select * from user where id = ?"
}
```