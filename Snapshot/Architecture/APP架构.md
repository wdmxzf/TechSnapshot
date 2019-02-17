## APP架构

![img](https://diycode.b0.upaiyun.com/photo/2018/deb6474517c316c33930518691dcc3ec.png)

* Model 层通常包括 model 对象 (在录音 app 中的例子是文件夹和录音对象) 和协调对象 (比如我们的 app 例子中的负责在磁盘上存储数据的 `Store` 类型)。被存储在磁盘上的那部分 model 我们称之为**文档 model**(documentation model)。
* 