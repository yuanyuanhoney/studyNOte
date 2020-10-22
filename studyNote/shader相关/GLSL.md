  glfwPollEvents();

 swapping buffers 双缓冲
	glfwSwapBuffers(window);
	可以设置缓存刷新时间：glfwSwapInterval(1);
处理事件存在有两个函数：
glfwPollEvents()和glfwWaitEvents();,前者会立即处理已经到位的事件，后者等



片段着色器

````glsl
#version 330 core
in vec3 ourColor;
in vec2 TexCoord;

out vec4 color;

uniform sampler2D ourTexture;

void main()
{
    color = texture(ourTexture, TexCoord);
    #mix(texture(texture1,TexCoord),texture(texture2,TexCoord),0.2). 
}
````

**我们使用GLSL内建的texture函数来采样纹理的颜色，它第一个参数是纹理采样器，第二个参数是对应的纹理坐标。texture函数会使用之前设置的纹理参数对相应的颜色值进行采样。这个片段着色器的输出就是纹理的（插值）纹理坐标上的(过滤后的)颜色。**



mix中最终输出颜色现在是两个纹理的结合。GLSL内建的mix函数需要接受两个值作为参数，并对它们根据第三个参数进行线性插值。。如果第三个值是`0.0`，它会返回第一个输入；如果是`1.0`，会返回第二个输入值。`0.2`会返回`80%`的第一个输入颜色和`20%`的第二个输入颜色，即返回两个纹理的混合色。

 ```glsl

 ```

