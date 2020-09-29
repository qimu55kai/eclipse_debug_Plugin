# eclipse_debug_Plugin
Eclipse show variables in a table or tree in debug perspective
@[TOC](eclipse debug matrix, array, tree plugin)

# Preface

Recently, there is a need to use eclipse to debug the java matrix, and see that the view as array of pycharm is very useful, as shown below.
![pycharm’s view as array](https://img-blog.csdnimg.cn/20200929114001692.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9zibG9nLmNzZ25nFF_center,color_pic_FF_tf_p_color,

But I did not find a similar eclipse plug-in on the Internet, so I wrote one by myself and shared it with everyone

# Show results
1. Eclipse first debug the java program to reach the specified breakpoint, as follows:
![](https://img-blog.csdnimg.cn/20200929114327303.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L25nLmNzZG4ubmV0L25nLmNzZG4ubmV0L25nLmNzBFF_size
2. Select the variable in Variables View and click! [](https://img-blog.csdnimg.cn/20200929144055112.gif#pic_center)
3. List display effect![](https://img-blog.csdnimg.cn/20200929144219285.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FF_center_color_center_FF_size,
4. Matrix display effect
![](https://img-blog.csdnimg.cn/20200929144219372.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L25nLmNzZG4ubmV0L25nLmNzZG4ubmV0L25nLmNzBFF_size
5. Tree view display
![](https://img-blog.csdnimg.cn/20200929144219304.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L25nLmNzZG4ubmV0L25nLmNzZG4ubmV0L25nLmNzBFF_size
6. Map display effect
![](https://img-blog.csdnimg.cn/20200929144219287.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L25nLmNzZG4ubmV0L25nLmNzZG4ubmV0L25nLmNzBFF_size
7. The java version of the DataFrame display effect![](https://img-blog.csdnimg.cn/20200929144606643.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9zibG9nLmNzZ25NYWBFF_color_tf_size pic_center)


# Custom java type settings

1. The plug-in can automatically identify arrays, matrices, and java types that implement java.lang.Iterable and java.util.Iterator. And convert it into a list.
2. For user-defined java types, it is necessary to provide methods or member variables whose return value is the java type included in 1, as shown in the following figure:
![](https://img-blog.csdnimg.cn/20200929145349228.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L25nLmNzZFFtp_color70FF_center,
3. The member variable can be written directly, and the method format is: method name () return value type. All types must have package name
4. If Column's name and Line's name are null, it means that 0,1,2,3,4......index values ​​are generated by default. If you need to customize, such as joinery.DataFrame row names and column names are obtained through the index method and the columns method, the configuration rules are as 3.
5. When displaying variables or objects in a tree diagram, there is no need to configure Column's name and Line's name

# Directions for improvement
1. Slow when displaying large matrices
2. No version adaptation, the eclipse version I developed is Mars.2 (4.5.2)
3. I don't know how the regular api interface recognizes the VariablesView window of debug and gets the current options. Now the method is not recommended, the code is shown in the figure:
![](https://img-blog.csdnimg.cn/2020092915173952.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L25nLmNzZFFtp_color70FF_center)
# Source code
Hard to force java programmers. I stayed up late at night to write by myself, the code is more casual. Share it with everyone, I hope you can help maintain it
# 中文介绍
[csdn](https://blog.csdn.net/xiaogong233/article/details/108865332)

