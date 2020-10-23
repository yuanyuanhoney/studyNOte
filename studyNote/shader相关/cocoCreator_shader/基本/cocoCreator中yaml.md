

yaml====>effect:

``` yaml
  CCEffect %{
  	techniques:
  	- passes:  //数组
      - vert: vs  //数组
      	frag: fs
        blendState:
        targets:
        - blend: true
      rasterizerState:
        cullMode: none
      properties://{}
        time: { value: 0.5 }
}%

```

**使用了yaml解析器，直接书写json也是可以的,yaml中所有的引号和逗号都可以省略但是冒号后的空格不可以省略；**

 ``` yaml
object1:
  key1: false
object2:
  key2: 3.14
  key3: 0xdeadbeef
  nestedObject:
    key4: 'quoted string'
 ```



另一个对我们的情况非常有用的 YAML 特性是数据间的引用与继承，先来看**引用**：

```yaml
object1: &o1
  key1: value1
object2:
  key2: value2
  key3: *o1
```

这个数据解析出来是这样的：

```json
{
  "object1": {
    "key1": "value1"
  },
  "object2": {
    "key2": "value2",
    "key3": {
      "key1": "value1"
    }
  }
}
```

再来**继承**

```yaml
object1: &o1
  key1: value1
  key2: value2
object2:
  <<: *o1
  key3: value3
```

解析为：

```json
{
  "object1": {
    "key1": "value1",
    "key2": "value2"
  },
  "object2": {
    "key1": "value1",
    "key2": "value2",
    "key3": "value3"
  }
}
```