#### 1. idea新建子目录后叠加而不是树形结构的解决方法

把 compact middle packages 前面的 勾 去掉

#### 2. 设置注释的双斜杠不在行首

进入 Settings -> Code Style -> Java ，在右边选择 “Code Generation” Tab，然后找到 Comment Code 那块，把
	Line comment at first column
	Block comment at first column
	去掉前面两个的复选框

#### 3. 关闭重复代码提示

inspections -> General -> duplicated code

#### 4. 去除sql语句黄色 背景

editor -> inspections -> sql -> no data sources configured ; sql dialect detection
		   -> color scheme -> general -> errors and warnings -> warning -> background
									  -> code -> injected language fragment -> background 

### 5. 大小写提示,小写也提示

![image-20200313170730795](G:\IDEA使用\idea-study\image\image-20200313170730795.png)

去掉那个勾



#### 6. springboot 项目 每次修改代码 都要重启项目 



```xml
<dependency>
   <groupId>org.springframework.boot</groupId>
   <artifactId>spring-boot-devtools</artifactId>
   <optional>true</optional> <!-- 表示依赖不会传递 -->
</dependency>


<plugin>
   <groupId>org.springframework.boot</groupId>
   <artifactId>spring-boot-maven-plugin</artifactId>
   <configuration>
      <fork>true</fork> <!-- 如果没有该配置，devtools不会生效 -->
   </configuration>
</plugin>
```

1. ctrl+Shift+Alt+/-----> 选择Registry ------>勾选

   

   compiler.automake.allow.when.app.running

2. 如果你进行上面的设置没有作用，请在检查下面图片的设置

   Setting--->Compiler--->勾选Build project automatically

---

- jeecg项目加了依赖 和 插件后报错了

---

#### 7. idea debug

F8 遇到方法不进入方法

F7 进入方法

ALT+F8 弹出可输入计算表达式调试框,输入具体的内容,可看到调试结果



#### 8. 设置注释格式

setting -> editor -> live templates -> 



#### 9. unmapped spring configuration



是web工程中的spring配置文件没有被IDEA所管理,

Ctrl+Shift+Alt+S”打开project的配置界面，选择“Modules”页签，再选择报“Unmapped Spring configuration files found.”的Module，点击“+”按钮



在弹出的窗口内，全部勾选Unmapped的Spring配置文件，点击“确定”，然后在父界面中点击“应用”或“确定”完成保存。

最后，重启IDEA后，发现"Event Log"不再提示“Unmapped Spring configuration files found.Please configure Spring facet.” ，结束



#### 10. 把自己写的util 打包

一、
在IDEA中选择File–>Project Structure，进入Project Structure窗口，在该窗口中，选择Artifacts，点击左侧的+号，选择JAR，选择Empty。如下图所示。

二、
上述步骤完成后，可以给新创建的Artifacts起一个名字，名字自己起。在左侧Artifacts列表栏中，点击你新创建的那个Artifacts，然后设置Output Directory，也就是打包后的Jar的输出路径（即Jar的存放路径），这里的输出路径可以自己设置，也可以使用默认的输出路径，只要你自己记得在哪里即可。
输出路径设置完毕后，点击Output Layout，然后点击下面的+号，再选择Directory Content。如下图所示。

三、
此时，会弹出一个路径选择框，让你选择需要打包的工具类的class文件，注意：是选择需要打包的工具类的class文件，而不是java文件。比如：你需要将DownloadUtils这一个工具类打成Jar包，那么这里你需要选择的路径是DownloadUtils.class所在的路径，而不是DownloadUtils.java所在的路径。
选择完毕后，点击OK。如下图所示。

四、
在IDEA最上面的菜单栏选择Build–>Build Artifacts此时会弹出一个窗口，让你选择哪个Artifacts，选择刚刚创建的那个Artifacts即可。然后点击右边小窗口的Build就可以了。如下图所示。

此时，去你设置的输出路径中查看，就可以看到有生成的Jar包了。





#### 11. 引入外部jar包

project structure -> libraties > + > java -> 选择外部jar包所在目录 -> ok