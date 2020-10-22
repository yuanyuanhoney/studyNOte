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



